## day01
### 项目构思
因为自己以前对node和webpack接触太少了，不得不说这个小项目布置下来让我很有压力，不仅仅是自己懂的知识太少了，而且还没有做过项目练手。
想做个小实例练练手，在网上找了好多原型之后，竟然茫然自己不知道做什么。记得自己在大学一个会上看见学长是用node做的一个聊天框，那就尝试开始自己的node生涯吧，哈哈哈
### 技术选型
谷歌了一下，这小小聊天框需要
1. Webpack的配置以及各个参数概念都有一定的熟悉
2. React+Webpack+Express的配合使用
3. 熟悉React的JSX语法、生命周期等的熟悉
4. Socket.io(入门)
5. localStorage(入门)
6. less(入门)

以上或多或少涉及到了吧。不知道自己会不会用到，只能一边做一边学，这就需要强大的学习能力。
所以今天先构思一下，祝自己加油！

## day02
### 初步搭建
因为自己是做聊天框，socket.io是必须的一个东西。大多数实时聊天系统通常基于 socket 来构建。 Socket 为客户端和服务器提供了双向通信机制。
Socket.IO 由两部分组成：
1. 一个服务端用于集成 (或挂载) 到 Node.JS HTTP 服务器： socket.io
2. 一个加载到浏览器中的客户端： socket.io-client
所以自己今天在看socket.io官方文档的过程中自己搭建了一个简陋的广播功能，同时打开两个浏览器窗口，在某一个窗口发送一个消息，另一个窗口可以看得到消息。但是有个弊端，自己发送消息自己也可以收得到，但是只要将消息发给除特定 socket 外的其他用户，可以用 broadcast 标志。最难的我感觉是react脚手架，自己不熟悉。
在接下来的时间里，自己想添加一个登陆功能，这样在聊天的时候就可以看得到谁和谁在聊天。
感觉自己要学的东西还有好多。加油加油！

## day03
### 编写项目
1. 更改服务启动相关配置(app.js)
删除routes/文件下的user.js，去掉app.js引入的userRouter、app.use('/users',userRouter)
更改视图渲染文件的类型:jade => html

node服务配置到这就完事了。
2. Webpack的配置
安装Webpack依赖:npm install webpack --save-dev
我当时很疑惑,如何知道把ReactApp组件render(渲染)到哪个html的id=app上呢？
原来这个和webpack的plugins(插件)的new HtmlWebpackPlugin有关。这个对象会读取一个目录下的html文件为模版，然后经过处理后再去output指定的目录输入一个新的html文件。因为在这里指定了/client/views/index.html文件为模板,所以react的所有都会渲染到这个html文件中。

要使webpack打包支持react和ES6语法还需要安装babel等依赖
枯燥的项目配置到此结束！

## day04
### 编写React组件
讲真！react对我来说简直太难了......以前直接没有接触过，只接触过vue。所以我必须得在白天学习node和webpack的时间里还要看react，而且无从下手，只能在网上看别人的教程例子。
在r-routes/index.js引用了一个根组件r_app,r_app再由组件AppHead、AppContent、AppFoot 构成。
在看别人写的页面例子中，难度很大。
要求懂一些react的语法啦。掌握一些基础知识:自定义组件、父子传值之类...
重要的是页面内容的呈现、逻辑的处理
有的项目一开始用到了react-redux,但是后面发现这绝对是高阶，但我们就想简简单单的做个聊天室，所以觉得没什么必要就直接跳过！！！
今天需要好好看看别人的例子，然后看懂。