# 第二天

## 今天的主要学习目标是如何在vue中安装并引入开发框架并能够自由引入官网的示例组件

- 在开始之前我有必要说一下，绝大部分的开发网站是需要翻墙才可以正常访问的，比如[GitHub](https://github.com)

- 翻墙，顾名思义，就是通过科学上网的方式，进行访问国外的网站，比如：[Google](https://www.google.com.hk/)等；

- 也可以通过修改本地DNS的方式进行部分网站的访问，如，在本地DNS中添加了8.8.8.8的DNS后可能可以进行访问GitHub
![DNS](./Images/DNS.png)

### 安装[Element-UI](https://element.eleme.io/#/zh-CN)

- 点击上方带有颜色的文字可以跳转到对应的官网。如无法访问，则需要翻墙

> 点击官网对应的导航 组件->安装即可看到以下界面
![element-ui文档](./Images/element-ui%E5%AE%98%E7%BD%91.png)

```
    npm i element-ui -S
```

### 打开命令工具，在昨天创建好的项目中执行以上命令会看到以下界面

- 安装时出现的界面
![安装](./Images/执行结果.png)

- 安装完成后验证是否安装完成，当仍然能够看到我们熟悉的地址时，即代表安装成功
![验证安装结果](./Images/验证执行结果.png)

- 此时打开项目，会发现在项目根目录下的“package.json”文件中会多出以下内容
![安装完成后对应的文件会多出的内容](./Images/项目中应该多出的内容.png)

- 在这里有一个需要注意的地方，是scrpits下的命令，这里包含项目打包命令、运行命令、自检测命令，左侧是明明名称，右侧是所需要执行的命令。例如：

```
    // 修改前
    "scripts": {
        "serve": "vue-cli-service serve",
        "build": "vue-cli-service build",
        "lint": "vue-cli-service lint"
    }

    // 修改后
    "scripts": {
        "s": "vue-cli-service serve",
        "b": "vue-cli-service build",
        "l": "vue-cli-service lint"
    }
```

- 在修改前，我们运行项目执行的是 npm run serve命令来打开localhost网址，但是我们修改后可通过 npm run s 来运行我们的项目。打包（build）和检测（lint）都是如此。这里不一定要改，如果图方便的话可以修改这里，这里有比较重要的东西。

### 在真正项目开发过程中如果需要区分项目的测试环境和正式环境的话就需要在这里配置环境。有可能启动命令和打包命令不止一个，有可能是四个，测试环境运行和打包两个命令，正式环境运行和打包两个命令。

## 当以上所有均显示正常时，即代表安装完毕。

#### package.json即是webpack包管理工具的常见操作，不过因为我们使用了vue脚手架的原因，框架已经为我们写好了包管理工具的内容。webpack包管理工具的主要作用是记录项目中所用到的所有工具、插件、UI库等工具的可视化的JSON文件。npm是包管理工具的下载工具。

### 打开项目前，我们要对VScode做一些小小的改动，如下图所示

![VScode的小改动](./Images/vsCode%E5%B0%8F%E6%94%B9%E5%8A%A8.png)

- 在界面中输入以下内容

```
    "workbench.startupEditor": "newUntitledFile",
    "window.zoomLevel": 1,
    "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
    "workbench.colorTheme": "Monokai",
    "editor.tabSize": 2,
    "editor.wordWrap": "on",
    "workbench.iconTheme": "vscode-icons"

    // 保存后关闭这个文件
```

#### 然后我们打开项目中的/src/App.vue和/src/main.js两个文件

- 在官网中继续往下查看，找到快速上手，并找到以下图片所示内容
![引入示例](./Images/引入element-ui.png)

### 继续看我们的代码，对比main.js文件中内容，将没有的内容全部粘贴到main.js中

# 切记！不要直接全部复制粘贴到main.js中！因为Windows和Mac甚至包括不同的vue版本、npm版本都会影响这个文件中的内容从而导致内容不一致，所以不要直接全部复制粘贴！

### 粘贴完成后我们在项目中再来运行npm run serve命令，只要不报错即可；

### 正式开始之前，我们先修改一下App.vue中的内容，将以下内容复制到文件中

```
<template>
    <div id="app">
        
    </div>
</template>

<script>

export default {
    data(){
        return{
            
        }
    }
}
</script>

<style>

</style>
```

### 随意从官网找到一个你喜欢的示例，并粘贴到App.vue中例如：

```
<template>
    <div id="app">
        <el-row>
            <el-col :span="24"><div class="grid-content bg-purple-dark"></div></el-col>
        </el-row>
        <el-row>
            <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="12"><div class="grid-content bg-purple-light"></div></el-col>
        </el-row>
        <el-row>
            <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="8"><div class="grid-content bg-purple-light"></div></el-col>
            <el-col :span="8"><div class="grid-content bg-purple"></div></el-col>
        </el-row>
        <el-row>
            <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
            <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
        </el-row>
        <el-row>
            <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="4"><div class="grid-content bg-purple-light"></div></el-col>
            <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="4"><div class="grid-content bg-purple-light"></div></el-col>
            <el-col :span="4"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="4"><div class="grid-content bg-purple-light"></div></el-col>
        </el-row>
    </div>
</template>

<script>

export default {
    data(){
        return{

        }
    }
}
</script>

<style>

    .el-row {
        margin-bottom: 20px;
    }

    .el-row:last-child{
        margin-bottom: 0;
    }

    .el-col {
        border-radius: 4px;
    }

    .bg-purple-dark {
        background: #99a9bf;
    }

    .bg-purple {
        background: #d3dce6;
    }

    .bg-purple-light {
        background: #e5e9f2;
    }

    .grid-content {
        border-radius: 4px;
        min-height: 36px;
    }

    .row-bg {
        padding: 10px 0;
        background-color: #f9fafc;
    }
</style>
```

- 我们能够在我们的网站中看到以下样式内容，和官网示例是一样即可。
![layout-style](./Images/layout-UI.png)

### 接下来去尝试一下其它的组件应该如何使用。