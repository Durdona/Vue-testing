<template>
  <header class="header">
    <a href="#" class="logo">
      <img :src="require('../assets/logo.png')" :alt="logo" /> 
    </a>
    <p>The sky was cloudless and of a deep dark blue...</p>
    <nav role="navigation">
      <ul id="menu">
        <li>
          <a href="#">Home</a>
        </li>
        <li>
          <a href="#">Gallery</a>
          <ul class="hidden">
            <li>
              <a href="#">app1</a>
            </li>
            <li>
              <a href="#">app2</a>
            </li>
            <li>
              <a href="#">app2</a>
            </li>
          </ul>
        </li>
        <li>
          <a href="#">About</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>


<style scoped>
@import url("https://fonts.googleapis.com/css?family=Jura");

.header {
  background: url("https://bit.ly/2CAkSKV") top right;
  padding: 10px;
  height: 130px;
}

div p {
  display: table-cell;
  font-size: 1em;
  font-family: "Jura", sans-serif;
  font-weight: 100;
  color: #b69f6e;
}

.logo {
  line-height: 200px;
}
.logo img {
  height: auto;
  width: 100px;
  float: left;
  margin-left: 20px;
  vertical-align: middle;
}

ul {
  list-style: none;
  position: absolute;
  margin: 0;
  padding: 0;
}
ul#menu {
  /*only this could move navigation to the right*/
  margin: 0;
  right: 0;
}

#menu > li {
  display: inline-block;
  margin-right: 1px;
  transition: all 0.5s ease;
}

#menu li a {
  display: block;
  min-width: 110px;
  height: 40px;
  line-height: 40px;
  text-align: left;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 80%;
  color: #b69f6e;
  transition: all 0.5s ease;
}

#menu li a:hover {
  color: #fbb829;
}

/*Style the second level dropdown links*/
li:hover ul a {
  background-color: #333;
  color: #fcffcd;
  height: 35px;
  line-height: 35px;
  text-align: left;
}

/* Hover state for dropdown anchor links */
li:hover ul a:hover {
  background-color: rgba(51, 51, 51, 0.6);
  background: url("https://bit.ly/2QfHrHi") top;
}

#menu ul li a:hover {
  color: black;
  font-weight: 400;
  transition: background 1s ease-out;
}

/*Hide dropdown links until they are needed*/
li ul {
  display: none;
}

/*Make dropdown links vertical*/
li ul li {
  display: block;
  float: none;
}

/*Prevent text wrapping*/
li ul li a {
  width: auto;
  min-width: 100px;
  padding: 0 15px;
}

/*Display the dropdown on hover*/
ul li a:hover + .hidden,
.hidden:hover {
  display: block;
}
</style>