<template>
  <!-- <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div> -->

    <TopNav/>
  
</template>

<script>

import TopNav from '@/components/TopNav.vue'

export default {
  props: [
    'state'
  ],
  components: {
    TopNav
  }
}
</script>


<style>

@import url(
  'https://fonts.googleapis.com/css2?family=Prompt:wght@100;200;300;400;500;600;700;800;900&display=swap'
  );

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #7F7F7F;
}
</style>
