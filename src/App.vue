<template>
  <div id="app"><HelloWorld /></div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import BlogPost from "./components/BlogPost";
import ServerPage from "./components/BlogPost";

export default {
  name: "App",
  components: {
    HelloWorld,
    BlogPost,
    ServerPage
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
