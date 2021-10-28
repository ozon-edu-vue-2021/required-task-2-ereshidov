<template>
  <div>
    <div class="folder" @click="toggleFolder">&#128193; {{ name }}</div>
    <div v-if="opened === true">
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
      type: String,
    },
  },
  data: () => ({
    opened: false,
  }),
  components: {
    Item: () => import("./Item.vue"),
  },
  methods: {
    toggleFolder() {
      this.opened = !this.opened;
    },
  },
});
</script>

<style scoped>
.folder {
  cursor: pointer;
}
</style>