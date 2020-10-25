<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>Latest questions from polls.</p>
    <Polls title="My Polls"></Polls>
  </div>
</template>

<script>
import Polls from "@/components/Polls";
export default {
  name: 'App',
  components: {
    Polls,
  }
}
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
</style>
