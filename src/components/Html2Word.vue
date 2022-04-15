<template>
    <div>
        <div id='source-html' v-show='false'>
            <slot name="content">
                <div>
                    {{ "没有内容呀~ 使用<slot name='content'></slot>来给文档添加内容" }}
                </div>
            </slot>
        </div>
        <div @click="exportHTML">
            <slot name="button">
                <button  class='btn btn-primary'>
                    {{ "下载" }}
                </button>
            </slot>
        </div>
    </div>
    
</template>

<script>
export default {
    name: 'Html2Word',
    methods:{
        /*
        * 将html转换为word
        */
        exportHTML(){
            let header = "<html xmlns:o='urn:schemas-microsoft-com:office:office' "+
                "xmlns:w='urn:schemas-microsoft-com:office:word' "+
                "xmlns='http://www.w3.org/TR/REC-html40'>"+
                "<head><meta charset='utf-8'><title>Export HTML to Word Document with JavaScript</title></head><body>";
            let footer = "</body></html>";
            let sourceHTML = header+document.getElementById("source-html").innerHTML+footer;
            
            let source = 'data:application/vnd.ms-word;charset=utf-8,' + encodeURIComponent(sourceHTML);
            let fileDownload = document.createElement("a");
            document.body.appendChild(fileDownload);
            fileDownload.href = source;
            fileDownload.download = 'document.doc';
            fileDownload.click();
            document.body.removeChild(fileDownload);
    },
    mounted(){
        this.exportHTML();
    }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
