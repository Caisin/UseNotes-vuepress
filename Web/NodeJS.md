# NodeJS



[[toc]]





## flag

* [NodeJs小册](https://nodejs.fasionchan.com/zh_CN/latest/index.html)

* [https://github.com/nodejs](https://github.com/nodejs)

* [https://nodejs.org/zh-cn](https://nodejs.org/zh-cn)



**WEB开发**

* [https://github.com/facebook/react](https://github.com/facebook/react) [https://reactnative.cn](https://reactnative.cn)

* [https://github.com/angular/angular](https://github.com/angular/angular) [https://angular.cn](https://angular.cn)


**原生应用开发**

* [https://github.com/topics/electron](https://github.com/topics/electron)
[https://github.com/electron/electron](https://github.com/electron/electron)

* [https://github.com/topics/nwjs](https://github.com/topics/nwjs)
[https://github.com/nwjs/nw.js](https://github.com/nwjs/nw.js)
[https://github.com/lxp135/NW.jsCnDocs](https://github.com/lxp135/NW.jsCnDocs)


* [https://github.com/Kagami/mpv.js](https://github.com/Kagami/mpv.js)



## 依赖管理


### 安装rpm


> npm与Node.js一起存在，这意味着当您下载并安装Node.js时，您会自动在计算机上安装npm

```bash
# 到https://github.com/nodesource/distributions#installation-instructions-1
# 复制更新软件源命令，并执行
curl -sL https://rpm.nodesource.com/setup_12.x | bash -
# 安装
yum install -y nodejs
# 检查Node.js和NPM版本
node -v && npm -v
```

### 安装NVM

> nodeJs版本管理工具,管理nodejs版本和npm版本

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
# 刷新
source ~/.bashrc
# 查询最新版本号
nvm ls-remote --lts
# 安装稳定版 Nodejs
nvm install <最新的版本号>
```

### 安装yarn

```bash
npm install -g yarn
```


### npm和yarn镜像

- 如果使用`yarn`，就把命令开头的`npm`替换为`yarn`

```bash
# 查看仓库地址
npm config get registry

# 设置官方仓库地址
npm config set registry https://registry.npmjs.org

# 设置淘宝镜像仓库地址
npm config set registry https://registry.npm.taobao.org

# 查看代理地址
npm config get proxy
npm config get https-proxy

# 设置代理地址
npm config set proxy http://127.0.0.1:1080
# 设置https代理地址
npm config set https-proxy http://server:port

# 设置代理用户名和密码
npm config set proxy http://username:password@server:port
npm confit set https-proxy http://username:password@server:port

# 删除代理地址
npm config delete proxy
npm config delete https-proxy
```


### yarn更新依赖包


- 更新所有到最新版本

> 推荐，不需要安装过多的依赖就可以达到目的

```bash
# 需要手动选择升级的依赖包，按空格键选择，a 键切换所有，i 键反选选择
yarn upgrade-interactive --latest
```

- 更新单个到指定版本

```bash
# yarn.lock和package.json都会更新，但是会进行版本锁定
yarn upgrade package@latest
```


### npm更新依赖包

> 更新`dependencies`到最新版本

```bash
# 先安装
npm install -g npm-check-updates
# 或者
yarn global add npm-check-updates
# 更新
npm-check-updates
# 或者
ncu -u
# 或者
ncu --upgrade
# 安装最新版本依赖
npm install
```


### 依赖管理

- yarn、npm命令简单比较

| npm                                | yarn                      | 说明                         |
|------------------------------------|---------------------------|----------------------------|
| npm install(i)                     | yarn                      | 安装                         |
| npm uninstall(un)                  | yarn remove               | 卸载                         |
| npm install xxx –-global(-g)       | yarn global add xxx       | 全局安装                       |
| npm install xxx –save(-S)          | yarn add xxx              | 安装包                        |
| npm install xxx –save-dev(-D)      | yarn add xxx –dev(-D)     | 开发模式安装包                    |
| npm update –save                   | yarn upgrade              | 更新                         |
| npm update –global                 | yarn global upgrade       | 全局更新                       |
| npm uninstall [–save/–save-dev]    | yarn remove xx            | 卸载                         |
| npm cache clean                    | yarn cache clean          | 清除缓存                       |
| rm -rf node_modules && npm install | yarn upgrade              | 重装                         |
| npm init                           | yarn init                 | 初始化某个项目                    |
| npm install/link                   | yarn install/link         | 默认的安装依赖操作                  |
| npm install koa --save             | yarn add koa              | 安装某个依赖，并且默认保存到package      |
| npm uninstall koa --save           | yarn remove koa           | 移除某个依赖项目                   |
| npm install koa --save-dev         | yarn add koa --dev        | 安装某个开发时依赖项目                |
| npm update koa --save              | yarn upgrade koa          | 更新某个依赖项目                   |
| npm install koa --global           | yarn global add koa       | 安装某个全局依赖项目                 |
| npm publish/login/logout           | yarn publish/login/logout | 发布/登录/登出，一系列NPM Registry操作 |
| npm run/test                       | yarn run/test             | 运行某个命令                     |





## 解析

```js
/**
 * https://www.npmjs.com/search?q=keywords:xml2js
 */

const fs = require("fs");
//模拟发送http请求
const request = require("request");
// npm install xpath
// https://github.com/yaronn/xpath.js
const xpath = require('xpath');

//get请求
request('https://jolx-1256021553.cos.ap-chengdu.myqcloud.com', function (error, response, body) {
    if (!error && response.statusCode == 200) {
        // npm install xmlreader
        // const xmlreader = require("xmlreader");
        // xmlreader.read(body, function (errors, res) {
        //     if (null !== errors) {
        //         console.log(errors)
        //         return;
        //     }
        //     console.log(res);
        // });

        // npm install xml2js
        // const Xml2js = require('xml2js');
        // const Parser = new Xml2js.Parser({ explicitArray: false, ignoreAttrs: false });

        // Parser.parseString(body, function (err, result) {
        //     console.log(result);
        // });

        // npm install xmldom
        // https://github.com/goto100/xpath
        // const dom = require('xmldom').DOMParser;
        // let doc = new dom().parseFromString(body);
        // console.log(doc);

        // npm install fast-xml-parser
        // const parser = require('fast-xml-parser');
        // const doc = parser.parse(body);
        // console.log(doc);

        // npm install xml-js
        const convert = require('xml-js');
        const doc = convert.xml2js(body);
        console.log(doc);
    }
});

//post请求
request({
    url: "https://jolx-1256021553.cos.ap-chengdu.myqcloud.com",
    method: "post",//如果是post就涉及到跨域的问题了
    json: true,
    headers: {
        "content-type": "application/json",
    },
    body: {
        account: 'admin',
        pwd: 'admin'
    }
}, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body);
    }
});
```



## 爬虫

### Puppeteer

* [https://github.com/GoogleChrome/puppeteer](https://github.com/GoogleChrome/puppeteer)

* [Puppeteer配置小记](https://www.itfanr.cc/2019/04/10/configuration-development-of-puppeteer)

- [xpath和css选择器](/Python/Python爬虫.md#xpath和css选择器)

- [`chromedriver`](/Python/Python爬虫.md#chromedriver)


## vue

![](/images/vue生命周期详解.png)


* [https://github.com/PanJiaChen/vue-element-admin](https://github.com/PanJiaChen/vue-element-admin)


