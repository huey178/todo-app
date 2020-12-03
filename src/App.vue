<template>
  <button @click="toggleDisplay" class="modalButton">Toggle Todo List</button>
  <transition name="fade">
    <ToDoComponent v-show="modalDisplayed" />
  </transition>
</template>

<script>
import ToDoComponent from "./components/ToDoComponent.vue";

export default {
  name: "App",
  components: {
    ToDoComponent,
  },
  data() {
    return {
      modalDisplayed: false,
    };
  },
  methods: {
    toggleDisplay() {
      if (this.modalDisplayed) {
        this.modalDisplayed = false;
      } else {
        this.modalDisplayed = true;
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.modalButton {
  margin-bottom: 5px;
}
</style>
