<template>
  <div id="app" class="h-100">
    <mainLayout />
    <footerLayout />
  </div>
</template>

<script>
import mainLayout from "./components/main.vue";
import footerLayout from "./components/footer.vue";
export default {
  name: "App",
  components: {
    mainLayout,
    footerLayout,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html,
body {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  border: none;
  overflow: auto;
}
</style>
