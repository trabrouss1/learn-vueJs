<template>
    <HomeP/>
</template>

<script>
import  HomeP from "./page/Home.vue";

export default {
  name: 'App',
  components: {
    HomeP
  }
}
</script>

<style>
@import url('./style/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto%3Awght%40300%3B400%3B700&display=swap');
#app {
  font-family: 'Roboto',Arial, sans-serif;
  padding: 20px;
}
</style>