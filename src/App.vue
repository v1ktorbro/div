<template>
  <Header />
  <Main title="они должны что-то знать" />
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
};
</script>

<style>
body {
  background-color: rgba(51, 51, 51, .15);
}
#app {
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  max-width: 1440px;
  display: flex;
  flex-direction: column;
  margin: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
