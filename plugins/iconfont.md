# 自定义字体图标

在 RN 中可以方便地使用自定义的图标，参考文章：[在 React Native 中快捷优雅使用 iconfont](https://www.jianshu.com/p/325d4b9955d3)

## 使用的工具及网站

* [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons)
* [fontello](http://fontello.com/)
* [iconfont - 阿里巴巴矢量图图标](http://www.iconfont.cn/)

## 配置步骤

#### 一\. 安装 react-native-vector-icons

```shell
yarn add react-native-vector-icons
```

react-native-vector-icons 内置了很多图标，如：FontAwesome、Foundation、Ionicons、MaterialIcons 等。

因此有如下两种使用方式

#### 二\. 使用内置图标

需要配置内置的字体文件，有自动和手动两种方式：

1\. 自动链接

```shell
react-native link
```

2\. 手动配置

参考官方的说明进行 iOS 和 Android 的配置：[官方 github](https://github.com/oblador/react-native-vector-icons)

#### 三\. 自定义字体 - iconfont

1\. 在  [iconfont - 阿里巴巴矢量图图标](http://www.iconfont.cn/) 上选择图标并下载

2\. 在 [fontello 网站](http://fontello.com/) 上，上传先前下载的 svg 文件，然后选中需要的字体并打包下载，主要是要得到 config.json 文件和 font 文件夹下的 fontello.ttf 文件

3\. 参考官方的说明进行 iOS 和 Android 的配置：[官方 github](https://github.com/oblador/react-native-vector-icons)。[安卓配置说明](https://github.com/oblador/react-native-vector-icons#option-manually-1)

## 四\. 使用

1\. 新建 fonts 文件夹，引入 config.json 文件

2\. 在 components 文件夹中新建 Icon.js 文件，内容如下：

```javascript
import { createIconSetFromFontello } from 'react-native-vector-icons';
import fontelloConfig from '../fonts/config.json';

export default Icon = createIconSetFromFontello(fontelloConfig);
```

3\. 在其他文件中引用 Icon 组件

```javascript
import Icon from "../components/Icon";

//阿里图标库中的图标 经fontello处理后 名称有了些许的改变 以config.json文件中的search字段为准
<Icon name={"roundcheck"} color={'#f00'} size={30}/>
<Icon.Button name="search" backgroundColor="#00f">按钮图标</Icon.Button>
<Text>内联 <Icon name="search" color="#f60"/> 图标</Text>
```

