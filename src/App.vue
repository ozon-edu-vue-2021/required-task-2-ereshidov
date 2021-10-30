<template>
  <div id="app">
    <div @click="handleClick">
      <item
        :type="fileTree.type"
        :contents="fileTree.contents"
        :name="fileTree.name"
        :target="fileTree.target"
      />
    </div>
  </div>
</template>

<script>
import Item from "./components/Item.vue";
import fileTree from "../public/static/node_modules.json";

const chosableTypes = ['file', 'link'];

export default {
  name: "App",
  components: {
    Item,
  },
  data() {
    return {
      fileTree,
      clickedItem: null,
    };
  },
  methods: {
    handleClick(event) {
      const shouldChangeColorOnClick = chosableTypes.includes(event.target.dataset?.type)

      if (shouldChangeColorOnClick) {
        if (this.clickedItem) {
          this.clickedItem.style.color = "inherit";
        }
        this.clickedItem = event.target;
        this.clickedItem.style.color = "red";
      }
    },
  },
};
</script>

<style>
</style>
