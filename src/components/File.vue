<template>
  <div>&#128441; {{ name }}</div>
</template>

<script>
import Vue from "vue";

export default Vue.extend({
  name: "File",
  props: {
    name: {
      type: String,
    },
  },
});
</script>

<style scoped>
</style>