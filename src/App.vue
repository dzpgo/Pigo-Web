<!-- <template>
  <div>
    <h1>我的Markdown编辑器</h1>
    <markdown-editor />
  </div>
</template> -->
<template>
  <div class="common-layout" style="height: 100%;">
    <el-container>
      <el-header height="30px" style="background-color: lightsteelblue;">        
        <el-icon :size="30">
          <House />
        </el-icon>
        <el-icon :size="30">
          <Search />
        </el-icon>
        <el-icon :size="30" :color="color">
          <Edit />
        </el-icon>
      </el-header>
      <el-container>
        <el-aside width="60px" style="height: 800px; background-color: lightcoral;">
          <el-icon :size="40"><Notebook /></el-icon>
          <el-icon :size="40"><Memo /></el-icon>
          <el-button :icon="Search" size="large" circle />
          <el-icon :size="40" style="padding: fixes; bottom: 0px;"><Tools /></el-icon>
        </el-aside>
        <el-aside width="200px" style="height: 800px; background-color:lightslategrey;">Aside2</el-aside>
        <el-container>
          <el-main>Main我的Markdown编辑器
            <markdown-editor />
          </el-main>
          <el-footer style="background-color: lightsteelblue;">Footer</el-footer>
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>



<script>
import MarkdownEditor from './components/MarkdownEditor.vue';
import { Search } from '@element-plus/icons-vue'
// import Menu from './components/Menu.vue'
export default {
  components: {
    MarkdownEditor,
    // Menu,
  },
  setup() {
    const urls = [
      'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg',
      'https://fuss10.elemecdn.com/1/34/19aa98b1fcb2781c4fba33d850549jpeg.jpeg',
    ];
    return {
      urls,
      Search,
    };
  },
};


</script>
<style scoped lang="css"></style>