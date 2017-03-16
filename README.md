
使用vue-cli脚手架搭建项目框架
----------------------------------------------------------
首先确保系统中安装node.js 4.x以上版本，npm 3.x以上版本
强烈推荐使用淘宝镜像：在命令行中输入 npm install -g cnpm --registry=http://registry.npm.taobao.org

安装vue-cli脚手架构建工具：cnpm install -g vue-cli

## 使用vue-cli创建项目模板
1.打开控制台进入项目存放目录，这里以项目存储路径为D:\git\ 为例

2.创建项目模板，其中webpack-simple为模板类型，vue-model为项目名称

vue init webpack-simple vue-model

创建成功后，将在git文件夹下看到vue-model文件夹，这就是vue-cli帮我们搭建的项目模板

3.安装所有依赖

cnpm install

4.执行项目

npm run dev

在模板中，有两个已经配置好的命令可以执行，一个是dev用作项目开发，一个是build用作生产环境，配置代码在package.json文件中的script属性。
执行成功后，浏览器自动打开http://localhost:8080/，并且支持热更新。

5.项目打包

npm run dist


组件开发
-------------------------------------------
下面就是开发组件的过程了，这里我先参考的mint-ui的代码，希望从中获取一些经验

以下是我的开发过程：

脚手架搭建好了，同时自动生成一个页面，就拿这个页面来试验吧

首先在阅读mint-ui的代码时，看到了大量使用ref，slot等vue特殊元素的代码，通过阅读官方文档可以知道ref用于给元素或子组件注册引用信息，甚至是引用一个组件！
而slot用于标记往哪个slot中插入子组件内容，这里可以使用slot定义一些默认内容，在使用者未定义内容时使用默认模板。


先开始动手编写弹窗外部框架和样式。
----------------------------------
这里以一个简单的button组件为例

`<button 
    :class="['vueButton ' + size]" 
>
    <slot>默认文字</slot>
</button>`

slot用于定义按钮默认文字
绑定class用于样式修改

这里先简单写了三种样式：big，middle，small

定义参数
`props: {
    size: {
        type: String,
        default: 'middle',
        validator (value) {
            return [
                'big',
                'small',
                'middle'
            ]
        }
    }
}`
这里定义参数为size，类型string，默认值为middle，值为big，middle和small

用法
引入并注册组件</br>
import vueButton from './components/vue-button.vue'</br>
components: {vueButton}

直接`<vueButton></vueButton>`即可 组件以默认参数middle和默认文字渲染

也可加上参数和文字使用
`<vueButton size='big'>`确认`</vueButton>`




