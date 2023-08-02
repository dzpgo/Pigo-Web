<template>
    <div>
        <el-input id="textcolor" type="textarea" v-model="markdown" :autosize="{ minRows: 6 }" placeholder="在此处输入您的Markdown内容..." />
        <div v-html="renderedMarkdown" ref="parsedMarkdown" />
    </div>
</template>
  
<script>
import { ref, computed, onMounted } from 'vue';
import { marked } from 'marked';
import hljs from "highlight.js"; // 引入 highlight.js
import "highlight.js/styles/monokai-sublime.css"; // 引入高亮样式 这里我用的是sublime样式
export default {
    setup() {
        const markdown = ref('');

        // 配置 marked 使用 highlight.js 进行语法高亮
        var rendererMD = new marked.Renderer();
        marked.setOptions({
            renderer: rendererMD,
            highlight: function (markdown) {
                return hljs.highlightAuto(markdown).value;
            },
            pedantic: false,
            gfm: true,
            tables: true,
            breaks: false,
            sanitize: false,
            smartLists: true,
            smartypants: false,
            xhtml: false
        });

        const renderedMarkdown = computed(() => {
            return marked(markdown.value);
        });

        // 在组件挂载后，初始化 highlight.js
        onMounted(() => {
            hljs.highlightAll();
        });
        return {
            markdown,
            renderedMarkdown,
        };
    },
};
</script>
  
<style>
/* 添加代码高亮样式 */
pre {
    padding: 1em;
    background: rgb(36, 36, 36);
    border-radius: 4px;
    overflow-x: auto;
}

code {
    font-family: 'Consolas', 'Courier New', monospace;
    color: #f5f5f5;
    /* 设置代码块的字体颜色 */
}
#textcolor{
    background-color: rgb(36, 36, 36);
    color: #f5f5f5;
}
</style>
  