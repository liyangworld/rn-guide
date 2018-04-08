# 搭建开发环境

开发环境的搭建参考官方文档。中文网有：

* [http://www.reactnative.org.cn/react-native/docs/getting-started.html]()
* [https://reactnative.cn/docs/next/getting-started.html]()

以上两篇文章差不多。

需要安装 Node、Python 2、JDK、Android Studio、Yarn、React Native的命令行工具（react-native-cli）。

## 一、安装 Node

在Windows平台上，可以使用 [nvm-windows](https://github.com/coreybutler/nvm-windows) 安装nvm以对电脑中的 Node 进行版本控制。在github上下载 nvm-setup.zip 文件安装即可。

安装之后便可以使用 nvm 下载各个版本的 Node。

## 二、安装 Python

ReactNative 要求安装 Python 2，但是貌似 Python 3也没问题。

在电脑上可以使用 Miniconda 对 Python 进行版本可控制。下载安装 Miniconda ，然后可以新增一个 Python环境。

## 三、安装 JDK

Android Studio 需要 Java Development Kit [JDK] 1.8 以上版本，可以在官网上下载安装，[jdk8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) ，配置java的系统变量。

## 四、安装 Android Studio

React Native目前需要 Android Studio 2.0或更高版本。安装时一定先要翻墙！！！（下载Android SDK大概1G多）。

参考上面的官方文档下载安装即可。

## 五、安装 Yarn 

参考官方文档即可，[安装 Yarn](https://yarn.bootcss.com/docs/install.html) 。Windows 上下载一份 `.msi` 文件安装。安装完成之后可以设置淘宝镜像。

```shell
yarn config set registry https://registry.npm.taobao.org --global
yarn config set disturl https://npm.taobao.org/dist --global
```

## 六、安装 react-native-cli

使用 npm 全局安装：

```shell
npm install -g react-native-cli
```





