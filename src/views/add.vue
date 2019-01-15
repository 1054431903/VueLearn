<template>
  <div>
    <p>head</p>
    <input type="text" v-model="title">
    <p>content</p>
    <input type="text" v-model="content">
    <br>
    <button @click="add()">add</button>
  </div>
</template>
<script>
import store from "@/store";
export default {
  name: "add",
  store,
  data() {
    return {
      title: "",
      content: ""
    };
  },
  methods: {
    add() {
      store.commit("addItem", {
        title: this.title,
        content: this.content
      });
      this.title = "";
      this.content = "";
      this.$router.push("/home/list");
    }
  }
};
</script>
<style scoped>
</style>
