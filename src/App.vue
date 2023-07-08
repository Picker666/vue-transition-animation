<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SingleComponent />
    <InitialTransition />
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import SingleComponent from './components/SingleComponent.vue';
import InitialTransition from './components/InitialTransition.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    SingleComponent,
    InitialTransition
  }
}
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
