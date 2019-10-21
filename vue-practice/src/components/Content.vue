<template>
  <div class="content">
    <transition name="fade" >
      <img
        @mouseover="hover=false"
        @mouseleave="hover = true"
        v-show="hover" v-cloak
        class="eiffel"
        :src="eiffel_tower"
        :alt="Eiffel_Tower"
        v-bind:style="{width: my_width + 'px'}"
      />
    </transition>
    <ul>
      <li v-for="infos in info" v-bind:key="infos">{{infos}}</li>
    </ul>
  </div>
</template>

<script>
import eiffel_tower from "../assets/eiffel_tower.jpeg";

export default {
  name: "Content",
  data() {
    return {
      hover: true,
      eiffel_tower: eiffel_tower,
      my_width: "300",
      info: [
        "Eifell Tower",
        "Constructed 1887-1889",
        "Located in Paris",
        "Height: 1063ft"
      ]
    };
  }
};
</script>

<style scoped>
div img.eiffel {
  padding: 30px;
  float: left;
  margin-right: 30px;
}

.content ul {
  padding-top: 30px;
  padding-left: 30px;
}

/* Vue Animation  */
.fade-enter {
  opacity: 0;
}
.fade-enter-active {
  transition: opacity 1s;
}

.fade-leave {
  opacity: 1;
}

.fade-leave-active {
  transition: opacity 1s;
  opacity: 0;
}
</style>
