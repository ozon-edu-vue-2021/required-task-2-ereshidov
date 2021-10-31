<template>
  <div data-type="link">&#128279; {{ name }}</div>
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
      type: String,
    },
  },
});
</script>

<style scoped>
</style>