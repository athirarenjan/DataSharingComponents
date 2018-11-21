<template>
  <div class="col-xs-12 col-sm-6">
    <h2>Server page</h2>
    <h2>2) Data shared through Event Bus</h2>
    i)Creating a global event bus
    <p v-if="!page">Please select a server</p>
    <p v-else>Server #{{ page.id }} selected,</p>
    <p>{{ page.body }}</p>
  </div>
</template>

<script>
import { serverBus } from "../main";

export default {
  name: "ServerPage",
  data() {
    return {
      page: null
    };
  },
  created: function() {
    serverBus.$on("pageSelected", page => {
      this.page = page;
    });
  }
};
</script>
