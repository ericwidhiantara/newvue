<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
  <PostRequest msg="Post Request Using Vue.js" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import PostRequest from "./components/PostRequest.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    PostRequest,
  },
};
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
