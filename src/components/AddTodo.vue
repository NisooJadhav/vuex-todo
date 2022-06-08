<template>
  <div id="top">
    <h3>Add Todo</h3>
    <div class="add">
      <form @submit="onSubmit">
        <input type="text" v-model="title" placeholder="add todo" />
        <input type="submit" value="Submit" />
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    },
  },
};
</script>

<style>
#top {
  text-align: center;
  padding-bottom: 25px;
}
h3 {
  padding-top: 10px;
  margin-top: 0;
  font-family: "oswald";
  font-size: 40px;
  color: #ffffff;
  text-shadow: 1px 2px 2px #000;
}
h3:hover {
  transform: translateY(-2px);
  transition: all 0.3s;
}
h3:not(:hover) {
  transform: translateY(2px);
  transition: all 0.3s;
}

.add {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
input[type="text"] {
  font-size: 20px;
  border-radius: 25px;
  padding-left: 25px;
  padding-top: 5px;
  padding-bottom: 5px;
  font-family: "Roboto";
}
input[type="submit"] {
  font-size: 20px;
  border-radius: 0px;
  background: #fff;
  border: none;
  padding: 10px;
  font-family: "Roboto";
  border-radius: 5px;
  margin-left: 10px;
  cursor: pointer;
}
input[type="submit"]:hover {
  box-shadow: 2px 2px 10px #5c0941;
  transform: translateY(-2px);
  transition: all 0.3s;
}
</style>