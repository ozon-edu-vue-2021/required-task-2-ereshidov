<template>
  <div :class="{ clicked }" @click="handleFileClick">&#128441; {{ name }}</div>
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
  data: () => ({
    clicked: false,
  }),
  methods: {
    handleFileClick() {
      this.clicked = true;
    },
  },
});
</script>

<style scoped>
.clicked {
  color: lightgreen;
}
</style>