<template>
  <NavBar />
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
    <transition name="fade">
      <Calendar v-show="calendarDisplayed" />
    </transition>
  </div>
</template>

<script>
import ToDoComponent from "./components/ToDoComponent.vue";
import Calendar from "./components/Calendar.vue";
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    ToDoComponent,
    Calendar,
    NavBar,
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
}
body {
  margin: 0;
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
