<template>
  <div id="app">
    <PageOrders />
  </div>
</template>

<script>
import PageOrders from './views/PageOrders.vue';

export default {
  name: 'App',
  data() {
    return {
      message: 'Hello World',
    };
  },
  components: {
    PageOrders,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
