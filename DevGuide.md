# 开发说明

## 开发环境
* Nodejs 6.5以上  [下载](https://nodejs.org/en/)
* Git cli

1. git地址 git clone https://github.com/banith/root.git
2. 确保已安装好nodejs,然后需要安装dva cli
3. 安装中使用淘宝镜像
npm config set registry https://registry.npm.taobao.org
npm info underscore
4.如果不行，换个镜像
npm install --registry=https://registry.cnpmjs.org
## 开发参考
http://web.jobbole.com/89688/  12步30分钟完成CRUD
## 创建步骤
*Step 1 安装 dva-cli ,查看安装后的版本
$ npm i dva-cli -g
$ dva -v
*Step 1.1 创建应用
$ dva new user-dashboard
$ cd user-dashboard
feedback
Success! Created user-dashboard at D:\2017\front\training\root\user-dashboard.

Inside that directory, you can run several commands:
  * npm start: Starts the development server.
  * npm run build: Bundles the app into dist for production.
  * npm test: Run test.

We suggest that you begin by typing:
  cd D:\2017\front\training\root\user-dashboard
  npm start

Happy hacking!

*Step 2 配置 antd 和 babel-plugin-import
babel-plugin-import 用于按需引入 antd 的 JavaScript 和 CSS，这样打包出来的文件不至于太大
$ npm i antd --save
$ npm i babel-plugin-import --save-dev

*Step 2.2修改 .roadhogrc，在 "extraBabelPlugins" 里加上：
       [
          "import", {
            "libraryName": "antd",
            "style": true
          }
        ]
 *Step3 配置代理，能通过 RESTFul 的方式访问http://localhost:8000/api/users
 修改 .roadhogrc，加上 "proxy" 配置：
"proxy": {
  "/api": {
    "target": "http://jsonplaceholder.typicode.com/",
    "changeOrigin": true,
    "pathRewrite": { "^/api" : "" }
  }
},
然后启动应用：(这个命令一直开着，后面不需要重启)
$ npm start
浏览器会自动开启，并打开 http://localhost:8000 。

访问 http://localhost:8000/api/users ，就能访问到
 http://jsonplaceholder.typicode.com/users 的数据。(由于 typicode.com 服务的稳定性，偶尔可能会失败。
 不过没关系，正好便于我们之后对于出错的处理)