<template>
  <div>
    <AddTodo />
    <FilterTodo />
    <Todos />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import FilterTodo from "./components/FilterTodo.vue";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
    FilterTodo,
  },
};
</script>

<style>
body {
  /* background: #8843f2; */
  background: linear-gradient(90deg, #8843f2, #a91079);
}
</style>