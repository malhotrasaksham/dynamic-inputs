<template>
  <div id="app">
    <template v-for="(value, index) in values">
      <input type="text" :key="index + 'input'" v-model="values[index]">
      <button @click="RemoveValue(index)" :key="index + 'button'">Delete</button>
    </template>
    <div>
      <button @click="AddValue()">Add Item</button>
    </div>
    {{values}}
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      values: []
    };
  },
  methods: {
    AddValue() {
      this.values.push(undefined);
    },
    RemoveValue(index) {
      this.values.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
