<template>
  <div class="todoModal">
    <p
      v-for="item in list"
      :key="item.id"
      :class="item.completed ? 'strike' : ''"
    >
      {{ item.todo }} <input type="checkbox" v-model="item.completed" />
    </p>
    <input
      placeholder="Add to List"
      v-model="item.todo"
      @keydown.enter="addItemToList"
    />
    <button @click="addItemToList">Add Task</button>
  </div>
</template>

<script>
const { v4: uuid_v4 } = require("uuid");
export default {
  data() {
    return {
      list: [],
      item: {
        todo: "",
        completed: false,
        id: uuid_v4(),
      },
    };
  },
  methods: {
    addItemToList() {
      if (this.item.todo.length > 0) {
        this.list.push(this.item);
        this.item = {
          todo: "",
          completed: "",
          id: uuid_v4(),
        };
      }
    },
  },
};
</script>

<style scoped>
button {
  margin-bottom: 5px;
}
input,
input:active {
  text-align: center;
  outline: none;
  margin: 10px;
}
.todoModal {
  margin: auto;
  max-width: 200px;
  min-height: 200px;
  background-color: teal;
  color: white;
  border-radius: 10px;
  box-shadow: 2px 2px 10px 1px grey;
}
.strike {
  text-decoration: line-through;
}
</style>
