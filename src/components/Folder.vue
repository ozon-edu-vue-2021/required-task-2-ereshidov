<template>
  <div>
    <div>&#128193; {{ name }}</div>
    <Item
      v-for="(item, i) in contents"
      :key="`${item.name}-${i}`"
      :contents="item.contents"
      :target="item.target"
      :name="item.name"
      :type="item.type"
      :indent="indent"
    />
  </div>
</template>

<script>
import Vue from "vue";

export default Vue.extend({
  name: "Folder",
  props: {
    name: {
      type: String,
    },
    contents: {
      type: Array,
      default: () => [],
    },
    indent: {
      type: String
    }
  },
  components: {
    Item: () => import('./Item.vue'),
  },
});
</script>

<style scoped>
</style>