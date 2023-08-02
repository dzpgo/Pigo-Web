<script setup>
import Article from './Article.vue'
import ArticleTabs from './ArticleTabs.vue'
import { ref } from 'vue'
const count = ref(0)
const load = () => {
  count.value += 2
}
</script>
<template>
    <div style="margin-left:5%;padding:1px;">
      
      <ul v-infinite-scroll="load" class="infinite-list" style="overflow: auto">
        <el-scrollbar>
          <!-- <li v-for="i in count" :key="i" class="infinite-list-item">{{ i }}</li> -->
        <li key="1"><a key="1" class="active">Ubuntu安装Docker</a></li>
        <li key="2"><a key="2">Docker安装Portainer</a></li>
        <li key="3"><a key="3">Docker安装Jellyfin</a></li>
        <li key="4"><a key="4">Watchtower-自动更新Docker镜像与容器</a></li>
        <li key="5"><a key="5">Docker安装Portainer</a></li>
        <li key="6"><a key="6">Docker安装Jellyfin</a></li>
        <li key="7"><a key="7">Docker安装Portainer</a></li>
        <li key="8"><a key="8">Docker安装Jellyfin</a></li>
        <li key="9"><a key="9">Docker安装Portainer</a></li>
        <li key="10"><a key="10">Docker安装Jellyfin</a></li>
        <li key="11"><a key="11">Docker安装Portainer</a></li>
        <li key="12"><a key="12">Docker安装Jellyfin</a></li>
        <li key="13"><a key="13">Docker安装Portainer</a></li>
        <li key="14"><a key="14">Docker安装Jellyfin</a></li>
        <li key="15"><a key="15">Docker安装Portainer</a></li>
        <li key="16"><a key="16">Docker安装Jellyfin</a></li>
        <li key="17"><a key="17">Docker安装Portainer</a></li>
        <li key="18"><a key="18">Docker安装Jellyfin</a></li>
        <li key="19"><a key="19">Docker安装Portainer</a></li>
        <li key="20"><a key="20">Docker安装Jellyfin</a></li>
        <li key="21"><a key="21">Docker安装Portainer</a></li>
        <li key="22"><a key="22">Docker安装Jellyfin</a></li>
        <li key="23"><a key="23">Docker安装Portainer</a></li>
        <li key="23"><a key="24">Docker安装Jellyfin</a></li>
        <li key="25"><a key="25">Docker安装Portainer</a></li>
        <li key="26"><a key="26">Docker安装Jellyfin</a></li>
        <li key="27"><a key="27">Docker安装Portainer</a></li>
        <li key="28"><a key="28">Docker安装Jellyfin</a></li>
      </el-scrollbar>
      </ul>
    </div>
<ArticleTabs></ArticleTabs>
   <!--  <Article></Article> -->
</template>

<style scoped>
body {
  margin: 0;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  width: 10%;
  background-color: #f1f1f1;
  position: fixed;
  height: 100%;
  overflow: auto;
}

li a {
  display: block;
  color: #000;
  padding: 8px 16px;
  text-decoration: none;
}

li a.active {
  background-color: #4CAF50;
  color: white;
}

li a:hover:not(.active) {
  background-color: #555;
  color: white;
}

/* 滚动条 */
.scrollbar-demo-item {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
  background: var(--el-color-primary-light-9);
  color: var(--el-color-primary);
}

/* Infinite Scroll 无限滚动 */
.infinite-list {
  list-style: none;
}
.infinite-list .infinite-list-item {
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--el-color-primary-light-9);
  color: var(--el-color-primary);
}
</style>