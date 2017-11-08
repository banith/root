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
## 常用命令
*安装 dva-cli ,查看安装后的版本
$ npm i dva-cli -g
$ dva -v
*创建应用
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