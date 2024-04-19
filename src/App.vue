<script setup>
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'

import About from './components/About.vue'
import ProjectList from './components/ProjectList.vue'
</script>

<template>
  <header class="header">
     <div class="myPhoto">
     </div>
     <div class="myInfo">
      <h2>盧瑄彤,LunaLu   <a href="mailto:lunausemail@gmail.com" class="send">傳送訊息</a></h2>
    
      <p>曾擔任遊戲代理公司一年半網頁美術，主要負責前端及UI/UX設計及網頁廣告製作，自我摸索將公司的技術從jquery提升至vue3，與後端laravel10成功合併。
        <br>腦袋對於前端複雜的邏輯，習慣用白話文的方式解說。</p>
       
     </div>
  </header>
  <About />
  <ProjectList />


</template>

<style lang="scss">
// You can import your SCSS file here
@import "@/assets/_header.scss";

</style>