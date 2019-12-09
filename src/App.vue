<template>
  <div id="app">
    <convert-to-jap></convert-to-jap>
  </div>
</template>

<script>
import ConvertToJap from "./components/ConvertToJap";

export default {
  name: 'app',
  components: {
    ConvertToJap
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
