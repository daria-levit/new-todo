<template>
  <div id="app">
    <MainComponent />
  </div>
</template>

<script>
  import MainComponent from './components/MainComponent.vue';
  export default {
    name: 'App',
    components: {
      MainComponent,
    },
  };
</script>

<style>
  #app {
    -webkit-font-smoothing  : antialiased;
    -moz-osx-font-smoothing : grayscale;
  }
  html {
    height : 100%;
  }
  body {
    background        : linear-gradient(45deg, #1d1838, #d0b5e8, #85ccec, #02335d);
    background-repeat : no-repeat;
    margin            : 0;
    padding           : 20px 0 0 0;
    font-family       : Arial, sans-serif;
  }
</style>