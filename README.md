<a href="https://wwp123.github.io/shopping-yanxuan/dist/#/home" target="_blank">PC 端可直接戳我进行预览哦~</a>

==注意== 因为无法搭建服务端，所以此预览无法进行注册和登录，建议下载食用更美味哦~

## 技术栈

vue2 + vue-cli + vuex + vue-router + webpack + ES6 + axios + stylus + mint-ui + koa + mongodb

## 项目运行

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run all tests
npm test
```

## 注意点

- 问题：启动服务，用本机 IP 无法访问此网站
- 解决方法： 在 bulid 目录下有一个 webpack.dev.config.js 的配置文件，发现 devServer 对象里的 host 属性取自 HOST || config.dev.host。查看 config.dev.host（按 ctrl 并点击 config.dev.host）自动跳转到 config 目录下的 index.js, 找到 dev 对象的 host 属性，默认是 localhost，把它改为 0.0.0.0，并重启服务即可

- 问题： webpack 设置跨域
- 解决方法： 在 config 目录下的 index.js 设置
  proxyTable: {
  '/api': {
  target: 'http://localhost:8888', //目标接口域名
  changeOrigin: true //是否跨域
  }
  }

## 说明

1.  本项目基于 vue-cli 搭建，利用 token 方式进行用户登录验证，并实现注册入库、读取用户等功能
2.  本地购物车数据使用 localstorage 进行存储，登录后与原有的购物车数据进行合并
3.  本项目使用 mongodb 作为后台数据库
