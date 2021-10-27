<template>
  <div>&#128279; <a v-bind:href="target">{{name}}</a></div>
</template>

<script>
import Vue from "vue";

export default Vue.extend({
  name: "Link",
  props: {
    name: {
      type: String,
    },
    target: {
      type: String
    }
  },
});
</script>

<style scoped>
</style>