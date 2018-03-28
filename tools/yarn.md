# Yarn基本使用

Yarn 是由 Facebook 开源的，类似于 npm 的包管理工具。[官网地址](https://yarnpkg.com/zh-Hans/docs/usage)

## 一\.初始化新项目

```shell
yarn init
```

## 二\.添加依赖包

```shell
yarn add [package]
yarn add [package]@[version]
yarn add [package]@[tag]
```

```shell
yarn add [package] --dev
yarn add [package] --peer
yarn add [package] --optional
```

## 三\.升级依赖包

```shell
yarn upgrade [package]
yarn upgrade [package]@[version]
yarn upgrade [package]@[tag]
```

## 四\.移除依赖包

```shell
yarn remove [package]
```

## 五\.安装项目依赖

```shell
yarn	//安装项目所有依赖
yarn install	//同 yarn
yarn install --force	//强制重新下载所有包
yarn install --production	//只安装生产环境依赖
```

