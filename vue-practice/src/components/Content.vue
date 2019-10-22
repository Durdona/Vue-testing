<template>
  <div class="column-layout">
    <div class="sidebars">
      <transition name="fade">
        <img
          @mouseover="hover=false"
          @mouseleave="hover = true"
          v-show="hover"
          v-cloak
          class="eiffel"
          :src="eiffel_tower"
          :alt="Eiffel_Tower"
          v-bind:style="{width: eiffel_width + '%'}"
        />
      </transition>
      <ul>
        <li v-for="infos in info" v-bind:key="infos">
          <span style="color: #094356;">&diams;</span>
          {{infos}}
        </li>
      </ul>
    </div>
    <div class="sidebars">
      <img
        calss="maddalena"
        :src="santa_maddalena"
        :alt="Santa_Maddalena"
        v-bind:style="{width: santa_width + '%'}"
      />
      <ul>
        <li v-for="infos in santa_info" v-bind:key="infos">
          <span style="color: #172507;">&starf;</span>
          {{infos}}
        </li>
      </ul>
    </div>
    <div class="sidebars">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa dignissimos velit dolor, esse quas vero quos? Non quis in necessitatibus, fuga sunt ea. Quia consectetur eius voluptatem quasi, totam voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum blanditiis adipisci quaerat saepe earum aliquid labore corrupti fuga fugit facilis alias assumenda commodi accusantium iste, maxime, id debitis, unde temporibus! Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus perferendis veniam officiis repellat voluptas laboriosam cupiditate provident rem dolores fugit quia eos consequatur, pariatur, deleniti totam ratione quis! Maiores, similique! Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, nisi. Dicta itaque, nesciunt tenetur quae repudiandae debitis laboriosam dolores dolor tempore quisquam. Corrupti itaque expedita hic corporis asperiores facere maiores.</p>
    </div>
  </div>
</template>


<script>
import eiffel_tower from "../assets/eiffel_tower.jpeg";
import santa_maddalena from "../assets/santa_maddalena.jpg";

export default {
  name: "Content",
  data() {
    return {
      hover: true,
      eiffel_tower: eiffel_tower,
      santa_maddalena: santa_maddalena,
      eiffel_width: "55",
      santa_width: "65",
      info: [
        "Eifell Tower",
        "Constructed 1887-1889",
        "Located in Paris",
        "Height: 1063ft"
      ],
      santa_info: ["Santa Maddalena", "Located in Italy", "Tiny Town Duloc"]
    };
  }
};
</script>

<style scoped>
.column-layout {
  display: flex;
  margin: 40px auto 0 auto;
  justify-content: space-between;
}
.sidebars {
  width: 30%;
  padding: 20px;
  box-sizing: border-box;
  position: relative;
  -webkit-box-shadow: 7px 7px 5px 0px rgba(82, 77, 82, 1);
  -moz-box-shadow: 7px 7px 5px 0px rgba(82, 77, 82, 1);
  box-shadow: 7px 7px 5px 0px rgba(82, 77, 82, 1);
}
img.eiffel,
img.maddalena {
  position: absolute;
  margin: auto;
}

.sidebars:nth-child(1) {
  /* background-color: rgba(197, 224, 220, 0.5); */
  background-color: rgba(107, 83, 78, 0.5);
}
.sidebars:nth-child(2) {
  /* background-color: rgba(248, 231, 201, 0.5); */
  background-color: rgba(107, 83, 78, 0.5);
}
.sidebars:nth-child(3) {
  /* background-color: rgba(160, 116, 225, 0.1); */
  background-color: rgba(107, 83, 78, 0.5);
}

ul {
  float: right;
  color: #f8ecc9;
  list-style-type: none;
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