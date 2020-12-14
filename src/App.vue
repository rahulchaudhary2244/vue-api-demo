<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <GetAPI/>
    <PostAPI/>
    <DeleteAPI/>
    <GetAPIById/>
    <PutAPI/>
  </div>
</template>

<script>
import GetAPI from './components/GetAPI.vue';
import PostAPI from './components/PostAPI.vue';
import DeleteAPI from './components/DeleteAPI.vue';
import PutAPI from './components/PutAPI'
import GetAPIById from './components/GetAPIById.vue';

export default {
  name: 'App',
  components: {
    GetAPI,
    PostAPI,
    DeleteAPI,
    GetAPIById,
    PutAPI,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
