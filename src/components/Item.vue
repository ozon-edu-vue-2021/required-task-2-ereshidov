<template>
  <div :style="style">
    <Folder
      :indent="indent"
      :contents="contents"
      :name="name"
      v-if="type === 'directory'"
    />
    <File :name="name" v-if="type === 'file'" />
    <Link :name="name" :target="target" v-if="type === 'link'" />
  </div>
</template>

<script>
import Vue from "vue";
import File from "./File.vue";
import Link from "./Link.vue";

export default Vue.extend({
  name: "Item",
  props: {
    type: {
      type: String,
    },
    name: {
      type: String,
    },
    contents: {
      type: Array,
      default: () => [],
    },
    target: {
      type: String,
    },
    indent: {
      type: Number,
      default: 10,
    },
  },
  computed: {
    style() {
      return "margin-left:" + this.indent + "px";
    },
  },
  components: {
    Folder: () => import("./Folder.vue"),
    File,
    Link,
  },
});
</script>

<style scoped>
</style>