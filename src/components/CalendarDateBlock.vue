<template>
  <div @dblclick="toggleActive" class="date-block">
    <p v-for="item in tasks.slice(0, 3)" :key="item.id">
      {{ item.item.slice(0, 7) }}...
    </p>
    <input
      v-if="isActive"
      v-model="task.item"
      placeholder="Add Task"
      @keyup.enter="
        addTaskToTasks();
        toggleActive();
      "
      id="taskInput"
    />
  </div>
</template>

<script>
const { v4: uuid_v4 } = require("uuid");
export default {
  data() {
    return {
      task: {
        item: "",
        id: uuid_v4(),
      },
      tasks: [],
      isActive: false,
    };
  },

  methods: {
    addTaskToTasks() {
      this.tasks.push(this.task);
      this.task = {
        item: "",
        id: uuid_v4(),
      };
    },
    toggleActive() {
      if (this.isActive) {
        this.isActive = false;
      } else {
        this.isActive = true;
      }
    },
  },
};
</script>

<style scoped>
.date-block {
  height: 80px;
  width: 80px;
  border-radius: 5px;
  background-color: rgb(112, 24, 37);
  margin: 0 0 5px 0;
  font-size: 0.7rem;
}

input,
input:active {
  width: 70%;
  outline: none;
}
p {
  color: white;
  margin: 0;
}
</style>
