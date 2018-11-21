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
    </div>
    <div><server-page></server-page></div>
  </div>
</template>
<script>
import { serverBus } from "../main";
import ServerPage from "../components/ServerPage";

export default {
  name: "BlogPost",
  data() {
    return {
      showServerPage: false
    };
  },
  components: { ServerPage },
  props: ["posts"],
  created: function() {},
  methods: {
    pageSelected: function(index) {
      this.showServerPage = true;
      serverBus.$emit("pageSelected", this.posts[index]);
    }
  }
};
</script>
