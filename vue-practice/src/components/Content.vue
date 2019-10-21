<template>
  <div class="content">
    <img
      class="eiffel"
      :src="eiffel_tower"
      :alt="Eiffel_Tower"
      v-bind:style="{width: my_width + 'px'}"
    />
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
</style>