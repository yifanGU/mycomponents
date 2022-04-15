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