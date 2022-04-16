# Html2Word 组件说明

#### 一、组件功能
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;这个组件实现的功能是将自定义的html转为word文件并输出，提供给用户下载。

#### 二、API
- 在父组件中，使用html-2-word组件.
```
    <html-2-word >
    </html-2-word>
```
- （可选）使用v-slot:content来标识位于组件中的内容。默认值 "没有内容呀~ 使用\<slot name='content'>\</slot>来给文档添加内容"
```
    <html-2-word >
        <template  v-slot:content >我是内容</template>
    </html-2-word>
```
- （可选）使用ref="button"来标识位于组件中的样式。你不需要为这个按钮绑定任何事件。这些逻辑已经在组件内部帮你处理好了。
```
    <html-2-word >
        <template v-slot:button>
            <button  class='btn btn-primary'>
                {{ "点我下载" }}
            </button>
        </template>
    </html-2-word>
```
- （可选）html-2-word中的内容在父组件完成加载的时候，就已经确定好了。如果父组件在html2-2-word组件渲染完成后，点击按钮前这个阶段发生了更新，那么就会造成导出的word内容过时的情况出现。所以，html-2-word允许传入一个回调函数，用来在导出word文档前更新v-slot：content中的内容。
```
父组件html模板中：
<html-2-word msg="Welcome to Your Vue.js App" :preLoad='getPicture'>
<template  v-slot:content>
    文字测试：
    我是内容
    图片测试：
    <img id='pictureLoader' src=''>
</template>

<template v-slot:button proLoad:getPicture >
    <button  class='btn btn-primary'>
        {{ "hhh下载" }}
    </button>
</template>
</html-2-word>
父组件的script标签中：
getPicture(){
      let img = document.getElementById("pictureLoader");
      img.src = "data:image/x-icon;base64,AAABAAEAICAAAAEAIAC......";
    }
  
```
