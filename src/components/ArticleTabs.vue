<template>
  <el-scrollbar style="height: 959px;">
    <div style="margin-left:16%;padding:1px 16px;height:5%;background:cadetblue;">
      <el-tabs v-model="editableTabsValue" type="card" editable class="demo-tabs" @edit="handleTabsEdit">
        <el-tab-pane v-for="item in editableTabs" :key="item.name" :label="item.title" :name="item.name">
          <!-- {{ item.content }} -->
          <div v-html="item.content"></div>
        </el-tab-pane>
      </el-tabs>
      <el-row class="mb-4">
        <el-button>Default</el-button>
        <el-button type="primary">Primary</el-button>
        <el-button type="success">Success</el-button>
        <el-button type="info">Info</el-button>
        <el-button type="warning">Warning</el-button>
        <el-button type="danger">Danger</el-button>
      </el-row>
    </div>
    <div style="margin-left:16%;">
      <Footer></Footer>
    </div>
  </el-scrollbar>
</template>
<script lang="ts" setup>
import { ref } from 'vue'
import Footer from './Footer.vue'
let tabIndex = 2
let dataHtml = `<div>
        <h1>全高的固定侧导航栏</h1>
        <h2>请尝试滚动此区域，并查看 sidenav 如何粘在页面上。</h2>
        <p>请注意，此 div 元素的左外边距为 25％。这是因为侧导航栏被设置为 25％ 宽。如果删除这个外边距，则 sidenav 将叠加到该 div 上。</p>
        <p>还要注意，我们已为 sidenav 设置 overflow：auto。如果 sidenav 太长时（例如，如果其中有超过 50 个链接），会添加滚动条。</p>
        <p>Some text..</p>
        <p>Some text..</p>
        <p>Some text..</p>
        <p>Some text..</p>
        <p>Some text..</p>
        <p>Some text..</p>
        <p>Some text..</p>
    </div>`
const editableTabsValue = ref('2')
const editableTabs = ref([
  {
    title: 'Tab 1',
    name: '1',
    content: dataHtml,
  },
  {
    title: 'Tab 2',
    name: '2',
    content: 'Tab 2 content',
  },
])

const handleTabsEdit = (targetName: string, action: 'remove' | 'add') => {
  if (action === 'add') {
    const newTabName = `${++tabIndex}`
    editableTabs.value.push({
      title: 'New Tab',
      name: newTabName,
      content: 'New Tab content',
    })
    editableTabsValue.value = newTabName
  } else if (action === 'remove') {
    const tabs = editableTabs.value
    let activeName = editableTabsValue.value
    if (activeName === targetName) {
      tabs.forEach((tab, index) => {
        if (tab.name === targetName) {
          const nextTab = tabs[index + 1] || tabs[index - 1]
          if (nextTab) {
            activeName = nextTab.name
          }
        }
      })
    }

    editableTabsValue.value = activeName
    editableTabs.value = tabs.filter((tab) => tab.name !== targetName)
  }
}
</script>
<style>
.demo-tabs>.el-tabs__content {
  padding: 32px;
  /* color: #6b778c; */
  font-size: 32px;
  font-weight: 600;
}

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
</style>