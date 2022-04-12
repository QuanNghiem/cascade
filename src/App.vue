<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <BankDashboard />
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import BankDashboard from "./components/dashboard/Dashboard.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    BankDashboard,
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
  margin-top: 60px;
}

body {
  font-size: 62.5;
}
</style>
