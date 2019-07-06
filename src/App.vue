<template>
  <div id="app">
    <navBar />
    <router-view />
    <footerBar />
  </div>
</template>

<script>
import navBar from "@/components/nav.vue";
import footerBar from "@/components/footer.vue";
export default {
  name: "home",
  components: { navBar, footerBar }
};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
