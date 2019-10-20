<template>
  <!-- has to have only one element inside, adding an extra div will cause error -->
  <div id="app">
    <Todos />
    <!-- Todos component -->
  </div>
</template>

<script>
import Todos from "./components/Todos";
export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todo: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo False",
          completed: false
        }
      ]
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
