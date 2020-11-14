<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png"/>
    <br>
    <h1>I have been clicked: {{ count }} times</h1>

    <button @click='count = count + 1'>Click to count</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data: () => ({
    count: 0
  })
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
