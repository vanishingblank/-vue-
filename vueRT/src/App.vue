<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<script>

</script>


<template>
  <header class="guide">
    

    <div >
      

      <nav >
        <RouterLink to="/">Cosmic</RouterLink> |
        
        
        <RouterLink to="/login">Login</RouterLink>|
        <RouterLink to="/game">Game</RouterLink>
      </nav>
    </div>
  </header>
<div class="pic">
  <RouterView />
</div>
</template>

<style scoped>
.guide{
  position:fixed;
  z-index: 1000;
  top:0;
  left:0;
  padding-bottom: 70px;
}
.pic{
  padding-top: 40px;
}
</style>
