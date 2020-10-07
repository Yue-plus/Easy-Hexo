---
title: 将主题上传至 NPM
---

# 将主题上传至 NPM <Badge text="@Yue-plus"/> <Badge text="Writing" type="warn"/>

## 注册账号

前往 npmjs.com [注册一个账号](https://www.npmjs.com/signup)，已有账号可前往[登陆](https://www.npmjs.com/login)

注册并登陆成功：

![npm](@img/4/4-3/01.jpg)

命令行登陆：

```sh
npm adduser
```

输入注册 npmjs.com 时的用户名、密码、邮箱。

## 安装 nrm

```sh
npm install nrm -g
```
> [nrm](https://github.com/Pana/nrm) 是 npm 仓库管理器，可用于快速切换 npm 仓库。

查看 npm 仓库：

```bash
$ nrm ls

* npm -------- https://registry.npmjs.org/
  yarn ------- https://registry.yarnpkg.com/
  cnpm ------- http://r.cnpmjs.org/
  taobao ----- https://registry.npm.taobao.org/
  nj --------- https://registry.nodejitsu.com/
  npmMirror -- https://skimdb.npmjs.com/registry/
  edunpm ----- http://registry.enpmjs.org/
```

使用官方 npm 仓库：

```bash
$ nrm use npm

   Registry has been set to: https://registry.npmjs.org/

```

## 修改主题文件夹内的 `package.json`

> [参考完整配置（英文）](https://docs.npmjs.com/files/package.json)

先在主题文件夹内执行：

```sh
npm init --scope=@<用户名> -y
```

`package.json` 文件示例：

```json {2,5-9}
{
  "name": "hexo-theme-arknights",
  "version": "1.2.1",
  "description": "一款明日方舟罗德岛阵营的 Hexo 主题",
  "author": "yue-plus <Yue_plus@foxmail.com> (https://github.com/Yue-plus)",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/Yue-plus/hexo-theme-arknights.git"
  },
  "license": "MIT",
  "bugs": {
    "url": "https://github.com/Yue-plus/hexo-theme-arknights/issues"
  },
  "homepage": "https://github.com/Yue-plus/hexo-theme-arknights#readme",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": []
}
```

::: warning
`package.json` 中
"name" 不能包含大写字母
:::

## 发布公共 NPM 包

```sh
npm publish --access public
```

## 使用主题

```sh
npm install <主题> --save
```

## 参考资料

> 1. [《npm发布包教程（一）：从npm说起》](https://segmentfault.com/a/1190000017461666)
> 2. [《npm发布包教程（二）：发布包》](https://segmentfault.com/a/1190000017463371)
> 3. [《npm发布包教程（三）：安装发布包》](https://segmentfault.com/a/1190000017472970)
> 4. [《npm发布包教程（四）：迭代》](https://segmentfault.com/a/1190000017477077)
> 5. [《npm发布包教程（五）：废弃/删除》](https://segmentfault.com/a/1190000017479985)
