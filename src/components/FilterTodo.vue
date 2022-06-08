<template>
  <div class="select">
    <select @change="filterTodos($event)">
      <option value="200">200</option>
      <option value="50">50</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "FilterTodos",
  methods: mapActions(["filterTodos"]),
};
</script>

<style>
select {
  width: 100px;
  height: 50px;
  font-family: "oswald";
  font-size: 25px;
}
.select {
  display: flex;
  justify-content: center;
  padding-bottom: 10px;
}
option {
  font-family: "oswald";
}
</style>