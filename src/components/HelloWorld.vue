<template>
  <div class="hello">
    <div>
      <h1>{{ msg }}</h1>
      <h2>Sharing data across Vuejs components</h2>
      <h2>1) Using props-parent to child</h2>
      <h5>API CALLS</h5>
    </div>
    <div><blog-post :posts="posts"></blog-post></div>
    <div></div>
  </div>
</template>

<script>
import BlogPost from "@/components/BlogPost";

export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Components In Detail",
      posts: null
    };
  },
  components: { BlogPost },
  created: function() {
    var vm = this;
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then(function(response) {
        return response.json();
      })
      .then(function(data) {
        vm.posts = data;
      });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
