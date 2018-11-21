<template>
  <div>
    <div>
      <ul style="height:200px;overflow:scroll;">
        <li v-for="(post, index) of posts" v-bind:key="post.id">
          <a
            href="javascript:;"
            style="cursor:pointer;"
            @click="pageSelected(index);"
          >
            <h3>{{ post.title }}</h3>
          </a>
          <p>{{ post.body }}</p>
        </li>
      </ul>
      <h2>2) Data shared through Event Bus</h2>
      i)Creating a global event bus
    </div>
  </div>
</template>
<script>
import serverBus from "@/main";

export default {
  name: "BlogPost",
  data() {
    return {};
  },
  props: ["posts"],
  created: function() {},
  methods: {
    pageSelected: function(index) {
      alert("clicked");
      serverBus.$emit("pageSelected", this.posts[index].body);
    }
  }
};
</script>
