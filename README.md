# gallery-by-react
a photo gallery project based on react
# gallery-by-react
## a photo gallery project based on react

基于React.JS架构的图片画廊应用
通过：
```
git clone https://github.com/jiang-jackson/gallery-by-react

```
将其克隆到本地，然后通过命令行：
`npm install`
安装项目需要的文件，安装完以后，WebStorm打开项目目录，点击run，运行项目文件里面的server.js文件。
完事会自动打开 http://localhost:8000/webpack-dev-server/ 可看效果


## 项目搭建

上面的有点简单粗暴，下面就仔细分析一下项目的具体搭建过程。

首先此项目依赖nodejs，所以要先装node的环境,可去[nodejs官网]([https://nodejs.org/en/](https://nodejs.org/en/))自行下载安装,也可以用nvm,brew等工具，想用什么方法随便你，这里不再赘述，如果这个都不能自己搞定，那基本不用入门了，可以直接放弃了……

首先安装脚手架工具yeoman
`npm install -g yo`
`yo —version` 可查安装版本

接下来去[yeoman官网](http://yeoman.io/)，点Discovering generators，搜索react，找到react-webpack，点进去进入到它的[github介绍主页](https://github.com/react-webpack-generators/generator-react-webpack#readme)（懒得上面步骤的，直接点这个可看，懒得看的，直接用下面命令安装这个generator即可

`npm install -g generator-react-webpack`

由于国外镜像，国内有时候下载慢或者下载不了，可以换成国内淘宝镜像,步骤如下：

``` 
1、npm install -g cnpm
2、cnpm install -g generator-react-webpack
```

安装完了就是使用了，使用之前呢，为了避免电脑宕机，可以为你自己的程序找到一个安身之所，我推荐选择github，我的地址是 [https://github.com/jiang-jackson](https://github.com/jiang-jackson)。

如果有github的创建一个仓库，用git clone 命令拷到本地来，首次使用git 命令，需要配置相应的用户名 邮箱。


然后在终端运行

`yo react-webpack gallery-by-react`

```
首先问我们
Please choose your application name (galleryProject)
	默认就是自己的工程，直接回车即可
Which style language do you want to use? 
❯ sass 
	这个地方会有几个选项，选sass
Enable postcss? (y/N) 
	这个要选y（yes），以后会解释
```

## 目录结构

打开工程，目录结构如下，这个与视频之中有点不一样，没了Gruntfile.js和webpack.dist.config.js，莫方，容我一一道来

![img](https://camo.githubusercontent.com/462e6799f0488b933d625e0e6ad54b4e422af3c9/68747470733a2f2f7374617469632e64696e6774616c6b2e636f6d2f6d656469612f6c414c4f616a33785f63304248637a7a5f3234335f3238352e706e675f363230783130303030713930672e6a7067)

```
cfg: 配置文件
dist: 项目发布所在目录
node_modules: 项目编译所需node组件所在的包
src: 源代码所在目录
test: 测试代码所在目录
.babelrc: 支持ES6(ES2015)的文件
.editorconfig: 用来统一不同的编辑器（IDE）的编码风格,具体可看官网http://editorconfig.org/
.eslintrc: 代码风格检测工具
.yo-rc.json: yeoman的配置文件，用来记录当前项目的一些信息，基本是刚才安装的时候那些选择的东西
karma.conf.js: karma测试框架的配置
package.json: node项目的配置文件，项目依赖的包都在这
server.js: 运行项目所必须的server文件
webpack.config.js: webpack开发环境配置文件，不过基本信息都放到了cfg目录下了，所以课程中老版本纳闷的同学们，不必太在意Gruntfile.js没有生成了
```

## 运行

这时候可以来一发运行了

```
npm start # or
npm run serve
```

自动跳到 http://localhost:8000/webpack-dev-server/ 成功

好了，环境已经搭好，下面就是具体的代码开发了。

开发的入口文件是src下的index.html和index.js，查看其中就可以发现./components/Main.js才是真正的主入口文件。

## 注意事项

- 刚开始的时候把post-css选为yes,因为课程中用到的autoprefixer-loader is deprecated，具体可看

  [https://github.com/passy/autoprefixer-loader](https://github.com/passy/autoprefixer-loader)

- .eslintrc文件里面可以加一些代码检查：

  比如我加了强制分号结尾

  ```
  "semi": [2, "always"],//语句强制分号结尾
  ```


- 调试react页面的时候可以选择React Developer Tools，可自行谷歌Chrome Web Store安装，可能需要翻墙的技能，没有也没关系。



