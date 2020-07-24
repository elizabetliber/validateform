<template>
  <div id="app">
      <lastName/>
  </div>
</template>

<script>
import lastName from '@/components/lastName'

export default {
  name: 'App',
  components: {
    lastName: lastName
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
