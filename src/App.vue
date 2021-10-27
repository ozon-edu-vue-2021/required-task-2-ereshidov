<template>
  <div id="app">
    <item
      :type="fileTree.type"
      :contents="fileTree.contents"
      :name="fileTree.name"
      :target="fileTree.target"
    />
  </div>
</template>

<script>
import Item from "./components/Item.vue";
import fileTree from "../public/static/node_modules.json";

export default {
  name: "App",
  components: {
    Item,
  },
  data() {
    return {
      fileTree,
    };
  },
};
</script>

<style>
</style>
