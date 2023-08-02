<script>
import ArticleList from './ArticleList.vue'
import Article from './Article.vue'
import { reactive, toRefs } from 'vue'

export default {
  ArticleList: {
    Article,
  },
  setup() {
    const state = reactive({
      fits: ['scale-down'],
      url: 'https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg',
    })

    const { fits, url } = toRefs(state)
    return {
      fits,
      url,
    };
  },
};


</script>

<template>
  <ul>
    <li style="margin-top: 5%; margin-left: 5%; margin-bottom: 10%;">
      <div class="demo-fit">
        <div v-for="fit in fits" :key="fit" class="block">
          <el-avatar shape="square" :size="80" :fit="fit" :src="url" />
        </div>
      </div>
    </li>

    <li>
      <a class="active" href="#home">首页</a>
      <!-- <router-link to="/home">首页</router-link> -->
    </li>
    <li>
      <!-- <a href="#Article">文章</a> -->
      <router-link to="/Article">文章</router-link>
    </li>
    <li>
      <!-- <a href="#contact">联系</a> -->
      <router-link to="/contact">联系</router-link>
    </li>
    <li>
      <!-- <a href="#about">关于</a> -->
      <router-link to="/about">关于</router-link>
    </li>
  </ul>

  <router-view></router-view>
  <!-- <ArticleList></ArticleList> -->
</template>

<script setup>
</script>

<style lang="css" scoped>
body {
  margin: 0;
}

ul {
  /* margin-top: 20%; */
  list-style-type: none;
  margin: 0;
  padding: 0;
  width: 5%;
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

.demo-fit {
  display: flex;
  text-align: center;
  justify-content: space-between;
}

.demo-fit .block {
  flex: 1;
  display: flex;
  flex-direction: column;
  flex-grow: 0;
}

.demo-fit .title {
  margin-bottom: 10px;
  font-size: 14px;
  color: var(--el-text-color-secondary);
}
</style>