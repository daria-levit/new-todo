<template>
  <v-app id="app">
      <v-content>
          <MainComponent/>
      </v-content>
    </v-app>
</template>

<script>
import MainComponent from "./components/MainComponent";

export default {
  name: 'App',
  components: {
    MainComponent
  },

  data: () => ({
    //
  }),
};
</script>

<style>

html {
height : 100%;
}
#app {
background        : linear-gradient(45deg, #1d1838, #d0b5e8, #85ccec, #02335d);
background-repeat : no-repeat;
margin            : 0;
padding           : 20px 0 0 0;
font-family       : Arial, sans-serif;
}

</style>