# vux-seed

[vux](https://github.com/airyland/vux) 是把weui（微信的前端库）用vue作的封装，并提供了一些额外的组件。

vue自身的脚手架项目[vue-cli](https://github.com/vuejs/vue-cli)本身已经非常好用，可以方便的创建一个完备的前端项目模板。

而此工程的目的是提供一个定制好的vux工程，方便直接通过`npm install`初始化一个可用的微信前端工程。

## 定制内容

1. 基于vue-cli创建工程，选择**webpack**作为打包工具。
2. 把vux，less直接加入工程的npm依赖。加入vux，可省去自己通过vue-cli创建工程后，需手动安装vux。加入less是因为vux中有使用。
3. 配置webpack，添加vux需要的babel loader。因为用vue-cli创建的webpack工程默认会通过`exclude: /node_modules/`把node_modules中的文件排除掉，而vue的源码却使用了一些es6的模块加载，因此对vux目录下的js文件需要添加此loader。[参考vux的文档](https://vuxjs.gitbooks.io/vux/content/install/vue.html)

## 使用

```
# 安装
npm install
# 调试
npm run dev
# 打包
npm run build
```

## 目录结构

```
.
├── build                      #构建脚本
│   ├── build.js                   #打包命令 npm run build 的入口。
│   ├── check-versions.js
│   ├── dev-client.js
│   ├── dev-server.js              #调试命令 npm run dev 的入口。
│   ├── utils.js
│   ├── webpack.base.conf.js       #webpack的主配置文件。
│   ├── webpack.dev.conf.js
│   └── webpack.prod.conf.js
├── config                     #build中用到的一些配置。
│   ├── dev.env.js
│   ├── index.js
│   └── prod.env.js
├── dist                       #打包文件输出目录。
├── index.html                 #根文档。1.webpack打包好的js会注入此文档。2.定义vue初始化用到的根dom。
├── package.json               #依赖描述。
├── src                        #源码目录
│   ├── App.vue                    #根组件，将components中的组件组合起来。
│   ├── assets                     #图片等静态资源
│   ├── components                 #页面组件。
│   └── main.js                    #入口，初始化vue。
└── static
```



## 工具

1. 代码高亮：sublime插件[vue-syntax-highlight](https://github.com/vuejs/vue-syntax-highlight)。vue使用的是以`vue`作为拓展名的单文本组件。