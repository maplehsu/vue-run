# 如何配置 vue + webpack + vue-cli 环境

<h2>第一步安装Node.js</h2>
<p>检查系统是否安装Node.js 指令：<strong>node -v</strong> 如果有版本号就是安装成功，没有安装的请去<a href="https://nodejs.org/en/download/" target="_blank">Node.js官网</a>下载</p>
<br>
<h2>第二步通过npm安装nrm来切换下载源</h2>
<p>为什么要换,你懂的!</p>
<p>输入全局安装指令 <strong>npm install -g nrm</strong></p>
<p>查看当前支持切换的源 <strong>nrm ls</strong> </p>
<p>切换指定的源taobao <strong>nrm use taobao </strong></p>
<br>
<h2>第三步npm安装yarn资源管理工具</h2>
<p><p><a href="https://yarn.bootcss.com/" target="_black" >Yarn</a></p> 是 Facebook, Google, Exponent 和 Tilde 开发的一款新的 JavaScript 包管理工具。就像我们可以从官方文档了解那样，它的目的是解决这些团队使用 npm 面临的少数问题，即：</p>
<p>安装的时候无法保证速度/一致性</p>
<p>安全问题，因为 npm 安装时允许运行代码</p>
<p>输入全局安装指令 <strong>npm install -g yarn</strong></p>
<p>安装成功即可查看版本 <strong>yarn -v</strong> </p>
<br>
<h2>第四步npm安装webpack</h2>
<p><a href="https://doc.webpack-china.org/guides/get-started/" target="_black" >webpack官网</a></p>
<p>输入全局安装指令 <strong>npm install --global webpack</strong></p>
<br>
<h2>第五步yarn安装vue-cli脚手架</h2>
<p>为什么要用vue-cli? vue-cli用于自动生成vue.js模板工程</p>
<p>输入全局安装指令 <strong>yarn global add vue-cli</strong></p>
<p>安装完毕后可执行命令 <strong>vue</strong>来查看vue指令</p>
<br>
<h2>第六步初始化vue项目</h2>
<p>使用yarn init指令初始化项目<strong>vue init &lt;template-name&gt; &lt;my-project&gt;</strong></p>
<p>&lt;template-name&gt;表示模板名称，vue-cli官方为我们提供了5种模板</p>
<p>使用指令<strong>vue list</strong>来查看5个模板名字和描述</p>
<p>1.&lt;webpack&gt;一个全面的webpack+vue-loader的模板，功能包括热加载，linting,检测和CSS扩展</p>
<p>2.&lt;webpack-simple&gt;一个简单webpack + vue-loader的模板，不包含其他功能，让你快速的搭建vue的开发环境</p>
<p>3.&lt;browserify&gt;一个全面的Browserify + vueify 的模板，功能包括热加载，linting,单元检测</p>
<p>4.&lt;browserify-simple&gt;一个简单Browserify + vueify的模板，不包含其他功能，让你快速的搭建vue的开发环境</p>
<p>5.&lt;simple&gt;一个最简单的单页应用模板</p>
<p>实际开发中建议使用&lt;webpack&gt;模板</p>
<p>使用指令<strong>vue init webpack &lt;my-project&gt;</strong></p>
<p>输入命令后，会询问我们几个简单的选项，我们根据自己的需要进行填写就可以了</p>
<p>Project name: 项目名称 ，如果不需要更改直接回车就可以了。注意：这里不能使用大写</p>
<p>Project description: 项目描述，默认为A Vue.js project</p>
<p>Author: 作者，如果你有配置git的作者，他会读取</p>
<p>Install vue-router? 是否安装vue的路由插件，我们这里需要安装，所以选择Y</p>
<p>Use ESLint to lint your code? 是否用ESLint来限制你的代码错误和风格</p>
<p>setup unit tests with  Karma + Mocha? 是否需要安装单元测试工具Karma+Mocha</p>
<p>Setup e2e tests with Nightwatch? 是否安装e2e来进行用户行为模拟测试</p>
<p>安装好了以后进入my-project目录里面指令<strong>cd my-project</strong></p>
<p>安装项目依赖包执行指令<strong>yarn</strong></p>
<br>
<p>Hello Vue</p>
<br>
<h2>Vue-cli 项目目录解析</h2>
<pre>
|-- build                            // 项目构建(webpack)相关代码
|   |-- build.js                     // 生产环境构建代码
|   |-- check-version.js             // 检查node、npm等版本
|   |-- dev-client.js                // 热重载相关
|   |-- dev-server.js                // 构建本地服务器
|   |-- utils.js                     // 构建工具相关
|   |-- webpack.base.conf.js         // webpack基础配置
|   |-- webpack.dev.conf.js          // webpack开发环境配置
|   |-- webpack.prod.conf.js         // webpack生产环境配置
|-- config                           // 项目开发环境配置
|   |-- dev.env.js                   // 开发环境变量
|   |-- index.js                     // 项目一些配置变量
|   |-- prod.env.js                  // 生产环境变量
|   |-- test.env.js                  // 测试环境变量
|-- src                              // 源码目录
|   |-- assets                       // 资源目录 
|   |-- components                   // vue公共组件
|   |-- store                        // vuex的状态管理
|   |-- App.vue                      // 页面入口文件
|   |-- main.js                      // 程序入口文件，加载各种公共组件
|-- static                           // 静态文件，比如一些图片，json数据等
|   |-- data                         // 群聊分析得到的数据用于数据可视化
|-- .babelrc                         // ES6语法编译配置
|-- .editorconfig                    // 定义代码格式
|-- .gitignore                       // git上传需要忽略的文件格式
|   |-- .postcssrc.js                // 通过JS插件装换样式的工具 
|-- README.md                        // 项目说明
|-- favicon.ico 
|-- index.html                       // 入口页面
|-- package.json                     // 项目基本信息
</pre>
