<template>
  <AppHeader :options="options" />
</template>

<script>
import AppHeader from "./components/AppHeader";
export default {
  components: { AppHeader },
  data() {
    return {
      options: ["Login", "About Us", "Home"],
    };
  },
};
</script>

<style>
body {
  margin: 0 !important;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
