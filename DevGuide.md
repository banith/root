# ����˵��

## ��������
* Nodejs 6.5����  [����](https://nodejs.org/en/)
* Git cli

1. git��ַ git clone https://github.com/banith/root.git
2. ȷ���Ѱ�װ��nodejs,Ȼ����Ҫ��װdva cli
3. ��װ��ʹ���Ա�����
npm config set registry https://registry.npm.taobao.org
npm info underscore
4.������У���������
npm install --registry=https://registry.cnpmjs.org
## �����ο�
http://web.jobbole.com/89688/  12��30�������CRUD
## ��������
*Step 1 ��װ dva-cli ,�鿴��װ��İ汾
$ npm i dva-cli -g
$ dva -v
*Step 1.1 ����Ӧ��
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

*Step 2 ���� antd �� babel-plugin-import
babel-plugin-import ���ڰ������� antd �� JavaScript �� CSS����������������ļ�������̫��
$ npm i antd --save
$ npm i babel-plugin-import --save-dev

*Step 2.2�޸� .roadhogrc���� "extraBabelPlugins" ����ϣ�
       [
          "import", {
            "libraryName": "antd",
            "style": true
          }
        ]
 *Step3 ���ô�����ͨ�� RESTFul �ķ�ʽ����http://localhost:8000/api/users
 �޸� .roadhogrc������ "proxy" ���ã�
"proxy": {
  "/api": {
    "target": "http://jsonplaceholder.typicode.com/",
    "changeOrigin": true,
    "pathRewrite": { "^/api" : "" }
  }
},
Ȼ������Ӧ�ã�(�������һֱ���ţ����治��Ҫ����)
$ npm start
��������Զ����������� http://localhost:8000 ��

���� http://localhost:8000/api/users �����ܷ��ʵ�
 http://jsonplaceholder.typicode.com/users �����ݡ�(���� typicode.com ������ȶ��ԣ�ż�����ܻ�ʧ�ܡ�
 ����û��ϵ�����ñ�������֮����ڳ���Ĵ���)