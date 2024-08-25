<template>
  <img alt="Vue logo" src="./assets/logo.png" height="50vH" />
  <Header msg="This is the header component" />
  <Todos msg="This is the To dos component" />
  <Footer msg="This is the footer component" />
</template>

<script>
import Todos from "@/components/TodoApp.vue";
import Header from "./components/HeaderComponent.vue";
import Footer from "./components/FooterComponent.vue";

export default {
  name: "App",
  components: {
    Header,
    Todos,
    Footer,
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
</style>
