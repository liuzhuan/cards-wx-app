# npm 📦

> 从小程序基础库版本 2.2.1 开始，小程序支持使用 npm 安装第三方包。

## 使用 npm 包

安装小程序包

```sh
$ npm install --production
```

此处务必使用 `--production` 选项，可以减少安装一些业务无关的 npm 包，从而减少整个小程序包的大小。

构建 npm。勾选「使用 npm 模块」选项。构建完成就可以使用 npm 包。

js 中引入 npm 包

```js
const package = require("pacakgeName");
const packageOther = require("packageName/other");
```

使用 npm 包中的自定义组件

```js
{
  "usingComponents": {
    "package": "packageName",
    "pacakge-other": "packageName/other"
  }
}
```

## 发布 npm 包

小程序的 npm 包有一些约束。

1. 小程序 npm 包要求根目录下必须有构建文件生成目录（默认为 `miniprogram_dist` 目录）。可以在 `pacakge.json` 中新增一个 `miniprogram` 字段来指定。

2. 小程序 npm 包里只有构建文件生成目录会被算入小程序包的占用空间，上传小程序代码时也只会上传该目录的代码。

3. 测试、构建相关的依赖请放入 devDependencies 字段中避免被一起打包到小程序包中。

## REF

- [npm 支持](https://developers.weixin.qq.com/miniprogram/dev/devtools/npm.html)