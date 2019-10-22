<template>
  <div id="app">
    <Header />
    <Content />
  </div>
</template>


<script>
import Header from "./components/Header";
import Content from "./components/Content"

export default {
  name: "Vue App",
  components: {
    Header, Content
  }
};
</script>




<style>
@import url("https://fonts.googleapis.com/css?family=Maven+Pro&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Maven Pro", sans-serif;
  line-height: 1.4;
}
body::after {
  content: "";
  background: url("https://bit.ly/2QfHrHi") right top;
  opacity: 0.7;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  z-index: -1;
}
</style>
