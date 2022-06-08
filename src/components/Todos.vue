<template>
  <div>
    <div class="top">
      <hr />
      <h3>ToDos</h3>
    </div>
    <div class="todos">
      <div v-for="todo in allTodos" :key="todo.id" class="todo">
        {{ todo.title
        }}<svg
          @click="deleteTodo(todo.id)"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 448 512"
        >
          <!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. -->
          <path
            d="M135.2 17.69C140.6 6.848 151.7 0 163.8 0H284.2C296.3 0 307.4 6.848 312.8 17.69L320 32H416C433.7 32 448 46.33 448 64C448 81.67 433.7 96 416 96H32C14.33 96 0 81.67 0 64C0 46.33 14.33 32 32 32H128L135.2 17.69zM31.1 128H416V448C416 483.3 387.3 512 352 512H95.1C60.65 512 31.1 483.3 31.1 448V128zM111.1 208V432C111.1 440.8 119.2 448 127.1 448C136.8 448 143.1 440.8 143.1 432V208C143.1 199.2 136.8 192 127.1 192C119.2 192 111.1 199.2 111.1 208zM207.1 208V432C207.1 440.8 215.2 448 223.1 448C232.8 448 240 440.8 240 432V208C240 199.2 232.8 192 223.1 192C215.2 192 207.1 199.2 207.1 208zM304 208V432C304 440.8 311.2 448 320 448C328.8 448 336 440.8 336 432V208C336 199.2 328.8 192 320 192C311.2 192 304 199.2 304 208z"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo"]),
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>

<style scoped>
hr {
  opacity: 30%;
  width: 90%;
  box-shadow: none;
  color: #fff;
}
h3 {
  padding-top: 10px;
  margin-top: 0;
  font-size: 40px;
  color: #ffffff;
  font-family: "oswald";
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
.todos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 1rem;
  padding-left: 150px;
  padding-right: 150px;
}
.todo {
  display: grid;
  background: #2f2f2f50;
  border: 1px solid #eee;
  padding: 1rem;
  border-radius: 10px;
  text-align: center;
  position: relative;
  cursor: pointer;
  font-size: 20px;
  font-family: "roboto";
  color: #ffffff;
  box-shadow: 1px 1px 10px #00000050;
}

svg {
  padding-left: 235px;
  width: 20px;
  color: #fff;
}
.top {
  text-align: center;
}
</style>