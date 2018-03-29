# 封装 Toast - toast.js

使用了第三方组件 [react-native-root-toast](https://github.com/magicismight/react-native-root-toast)。

```javascript
'use strict';

import Toast from 'react-native-root-toast';

const defaultOptions = {
    duration: 1000,
    backgroundColor: "rgba(0,0,0,.8)"
};

export default function (msg, options) {
    options = Object.assign({}, defaultOptions, options);
    return Toast.show(msg, options);
}
```

