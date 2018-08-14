# nuxt-admin

> Nuxt.js project

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install*[see note below]

# serve with hot reload at localhost:3000 默认端口
$ npm run dev

# build for production and launch server 配置端口 PORT=4000
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

*Note: Due to a bug in yarn's engine version detection code if you are
using a prerelease version of Node (i.e. v7.6.0-rc.1) you will need to either:
  1. Use `npm install`
  2. Run `yarn` with a standard release of Node and then switch back

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).

# 部署 （以nuxt为例）（来源自网上，有待解决）

- 基础模板的部署方式
何为基础模板？使用了 vue init nuxt-community/starter-template <project-name> 进行搭建的！

- 第一步，打包
在执行 npm run build 的时候， nuxt 会自动打包。

- 第二步，选择要部署的文件（社友最关心的步骤）：
.nuxt/ 文件夹
package.json 文件
nuxt.config.js 文件(如果你配置proxy等，则需要上传这个文件，建议把它传上去)
build/ 文件夹

- 第三步，启动你的nuxt：
使用pm2启动你的nuxt.js：

$ npm install // or yarn install 如果未安装依赖或依赖有更改
$ pm2 start npm --name "nuxt-admin" -- run start

# 部署方案 二 （不靠谱）
代码前期准备
1.在本地执行命令:npm run build 生成 .nuxt目录
2.配置package.json文件新增

```
  "config": {
    "nuxt": {
      "host": "0.0.0.0",
      "port": 80
    }
  }
```
 3.在/home下创建app文件夹,将上一步生成的.nuxt文件和package.json、server等文件上传到该文件夹
.nuxt/
server/
build/
package.json
nuxt.config.js