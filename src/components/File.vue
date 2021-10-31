<template>
  <div data-type="file" :class="{ clicked }">&#128441; {{ name }}</div>
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
  },
});
</script>

<style scoped>
.clicked {
  color: lightgreen;
}
</style>