<template>
  <button
    @click="
      modalDisplayed === true
        ? (modalDisplayed = false)
        : (modalDisplayed = true)
    "
    class="toggleButton"
  >
    Toggle Todo List
  </button>
  <transition name="fade">
    <ToDoComponent v-show="modalDisplayed" />
  </transition>
  <div class="calendar">
    <button
      @click="
        calendarDisplayed === true
          ? (calendarDisplayed = false)
          : (calendarDisplayed = true)
      "
    >
      Toggle Calendar
    </button>
    <Calendar v-if="calendarDisplayed" />
  </div>
</template>

<script>
import ToDoComponent from "./components/ToDoComponent.vue";
import Calendar from "./components/Calendar.vue";

export default {
  name: "App",
  components: {
    ToDoComponent,
    Calendar,
  },
  data() {
    return {
      modalDisplayed: false,
      calendarDisplayed: false,
    };
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
.toggleButton {
  margin-bottom: 5px;
}
</style>
