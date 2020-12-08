<template>
  <nav>
    <h1>Productivity App</h1>
    <div>
      <ul>
        <li><button>Toggle To Do List</button></li>
        <li><button>Toggle Calendar</button></li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
h1 {
  padding: 0 10px 0 10px;
  float: left;
}
li {
  float: left;
  padding: 10px;
}
nav {
  background-color: blue;
  color: white;
  overflow: hidden;
  text-align: left;
  align-items: center;
}
ul {
  list-style: none;
}
</style>
