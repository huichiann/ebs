<template>
  <v-app>
    <div id="app">
        <router-view/>
    </div>
  </v-app>
</template>

<script>


export default {
  name: 'App',

  components: {

  },

  data: () => ({
    //
  }),
};
</script>

<style>
#app {
    height: 100vh;
}
</style>
