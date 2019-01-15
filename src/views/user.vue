<template>
  <div>
    user<br>
    <button @click="add()">add</button>
  </div>
</template>
<script>
export default {
  name: "user",
  methods: {
    add() {
      this.$router.push("/add");
    }
  }
};
</script>
<style scoped>
</style>
