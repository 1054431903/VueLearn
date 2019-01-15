<template>
  <div>
    <ul>
      <li
        v-for="(item, index) in lists"
        :key="index"
        @click="choose(index)"
        :class="{active : index == current && current !== ''}"
      >{{item}}</li>
    </ul>
    <button @click="add()">add</button>
    <ul>
      <li v-for="(item, index) in items" :key="index">{{item}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "demo1",
  data() {
    return {
      current: "",
      lists: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      items: []
    };
  },
  methods: {
    choose(index) {
      this.current = index;
    },
    add() {
      if (this.current !== '') {
        this.items.push(this.lists[this.current]);
        this.current = "";
      }
    }
  }
};
</script>
<style>
li.active {
  background: #00ffff;
}
</style>