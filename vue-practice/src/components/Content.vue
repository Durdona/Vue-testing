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
          v-bind:style="{width: my_width + '%'}"
        />
      </transition>
      <ul>
        <li v-for="infos in info" v-bind:key="infos">{{infos}}</li>
      </ul>
    </div>
    <div class="sidebars">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus unde soluta, molestiae dignissimos iure dolor, ullam neque ratione accusamus praesentium quasi aperiam sapiente minus enim, voluptatibus eius officiis architecto consequatur. Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eius architecto suscipit sunt tempore blanditiis est consequuntur placeat molestiae vitae veniam labore non praesentium perspiciatis mollitia molestias minima, tenetur ipsum saepe? Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti repudiandae velit ratione ipsum laudantium nulla quidem sunt pariatur provident qui, exercitationem corporis unde sed, sequi quisquam nesciunt, asperiores commodi. Expedita.</p>
    </div>
    <div class="sidebars">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa dignissimos velit dolor, esse quas vero quos? Non quis in necessitatibus, fuga sunt ea. Quia consectetur eius voluptatem quasi, totam voluptates. Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum blanditiis adipisci quaerat saepe earum aliquid labore corrupti fuga fugit facilis alias assumenda commodi accusantium iste, maxime, id debitis, unde temporibus! Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloribus perferendis veniam officiis repellat voluptas laboriosam cupiditate provident rem dolores fugit quia eos consequatur, pariatur, deleniti totam ratione quis! Maiores, similique! Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, nisi. Dicta itaque, nesciunt tenetur quae repudiandae debitis laboriosam dolores dolor tempore quisquam. Corrupti itaque expedita hic corporis asperiores facere maiores.</p>
    </div>
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
      my_width: "60",
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
.column-layout {
  display: flex;
  margin: 40px auto 0 auto;
  justify-content: space-between;
}
.sidebars {
  width: 30%;
  padding: 20px;
  box-sizing: border-box;
}

.sidebars:nth-child(1) {
  background-color: rgba(197, 224, 220, 0.3);
}
.sidebars:nth-child(2) {
  background-color: rgba(248, 231, 201, 0.4);
}
.sidebars:nth-child(3) {
  background-color: rgba(160, 116, 225, 0.1);
}

ul {
  float: right;
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