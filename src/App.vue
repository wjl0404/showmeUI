<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
// import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue'
import Test from './components/Test'
import SButton from './button/src/Button'
import VirtualList from './components/VirtualList.vue'
import SBaseModal from './modal/base-modal'
import STabs from './tab/tabs'
import STab from './tab/tab'
import SPopover from './popover/popover'
import SSpace from './space/src/space'

const modalVisible = ref(false)

// const open = () => {
//   modalVisible.value = true
// }

const activeTab = ref('tab1')

const visible = ref(false)
const host = ref()
const open = () => {
  visible.value = !visible.value
}
</script>

<template>
  <test></test>
  <s-button type="primary">确定</s-button>
  <SButton>取消</SButton>
  <h1 class="text-3xl font-bold underline">Hello world!</h1>
  <VirtualList></VirtualList>
  <button @click="open">打开</button>
  <SBaseModal v-model="modalVisible">
    <div
      style="
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translateY(-50%) translateX(-50%);
      "
    >
      <img src="./assets/sheep.webp" />
    </div>
  </SBaseModal>
  <s-tabs v-model="activeTab" closable addable>
    <s-tab id="tab1" title="Tab1">Tab1 Content</s-tab>
    <s-tab id="tab2" title="Tab2">Tab2 Content</s-tab>
    <s-tab id="tab3" title="Tab3">Tab3 Content</s-tab>
  </s-tabs>
  <div ref="host" class="host" @click="open">host</div>
  <SPopover v-model="visible" :host="host" title="Title" show-arrow
    >overlay</SPopover
  >
  <div>
    <s-button type="primary">1123</s-button>
    <s-space align="center" fill>123124</s-space>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
