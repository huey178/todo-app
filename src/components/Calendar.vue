<template>
  <div class="calendar">
    <span> <CalendarDateBlock v-for="i in 7" :key="i" /> </span>
  </div>
</template>

<script>
import CalendarDateBlock from "./CalendarDateBlock.vue";

export default {
  components: {
    CalendarDateBlock,
  },
};
</script>

<style>
.calendar {
  margin: auto;
}
</style>
