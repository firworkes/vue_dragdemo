<template>
  <div id="app">
    <!-- <MoveDom/> -->
    <ButtonMove/>
  </div>
</template>

<script>
// import MoveDom from './view/MoveDom';
import ButtonMove from './view/ButtonMove';

export default {
  name: 'App',
  components: {
    // MoveDom
    ButtonMove
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
