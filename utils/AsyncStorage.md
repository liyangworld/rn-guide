# 封装本地存储 AsyncStorage - Storage.js

RN 提供的 AsyncStorage 可以根据 key 存储相应的字符串，此处封装一下，使用 JSON.stringify 使其能够存储数组和对象。

```javascript
'use strict';

import { AsyncStorage } from 'react-native';

/**
 * 获取存储的数据
 * @param {*} key 
 */
exports.getItem = async (key) => {
    let item = await AsyncStorage.getItem(key);
    if (!item) {
        return undefined;
    }
    return JSON.parse(item).v;
}
/**
 * 存入数据
 * @param {*} key 
 * @param {*} value 
 */
exports.setItem = (key, value) => AsyncStorage.setItem(key, JSON.stringify({
    v: value
}));

/**
 * 删除已经存在的数据
 * @param {*} key 
 */
exports.removeItem = (key) => AsyncStorage.removeItem(key);

/**
 * 清除所有
 */
exports.clear = () => AsyncStorage.clear();

/**
 * 获取所有的key
 */
exports.getAllKeys = () => AsyncStorage.getAllKeys();
```

