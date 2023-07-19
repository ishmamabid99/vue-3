<template>
  <AppHeader :options="options" />
  <AppFooter/>
</template>

<script>
import AppHeader from "./components/AppHeader";
import AppFooter from "./components/AppFooter";
export default {
  components: { AppHeader, AppFooter },
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
  font-family: "Space Grotesk", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
