<template>
  <v-app
          id="app"
          class="mx-0"
  >
      <v-content class="pt-5">
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
font-family       : Arial, sans-serif;
}

</style>