# 像素转尺寸 - px.js

开发时默认手机屏幕宽度为 750 像素，设计稿也按宽度 750 像素进行设计，然后按照实际设备像素进行比例缩放。

```javascript
'use strict';

import {
    Dimensions,
    Platform,
    PixelRatio
} from 'react-native';

const deviceWidth = Dimensions.get('window').width;

export default function px(size) {
    if (PixelRatio.get() >= 3 && Platform.OS == 'ios' && size == 1) {
        return size;
    }
    return deviceWidth / 750 * size;
}
```

