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
        <li v-for="infos in eiffel_info" v-bind:key="infos">
          <span style="color: navy">&diams;</span>
          {{infos}}
        </li>
      </ul>
      <h3>Paris Eifell Tower</h3>
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
          <span style="color: green;">&starf;</span>
          {{infos}}
        </li>
      </ul>
      <h3>Italy Santa Maddalena</h3>
    </div>
    <div class="sidebars">
      <h3>{{header}}</h3>
      <p>{{reversed}}</p>
      <p>{{reversed.split('').reverse().join('')}}</p>
      <h4>Attribute Binding</h4>
      <ul>
        <li v-for="list in binding" v-bind:key="list"><span style="color: navy">&diams; </span>{{list}}</li>
      </ul>
    </div>
  </div>
</template>


<script>
import eiffel_tower from "../assets/eiffel_tower.jpeg";
import santa_maddalena from "../assets/santa_maddalena.png";

export default {
  name: "Content",
  data() {
    return {
      hover: true,
      eiffel_tower: eiffel_tower,
      santa_maddalena: santa_maddalena,
      eiffel_width: "65",
      santa_width: "65",
      eiffel_info: [
        "Eifell Tower",
        "Built 1887-1889",
        "Located in Paris",
        "Height: 1063ft"
      ],
      santa_info: ["Santa Maddalena", "Located in Italy", "Tiny Town Duloc"],
      header: "Reversed Sentence",
      reversed: "Today is Tuesday... Learning Vue JS is interesting",
      binding: [
        ":alt='description'",
        ":href='url'",
        ":title='toolTip'",
        ":calss='isActive'",
        ":style='isStyled'",
        ":disabled='isDisabled'"
      ]
    };
  }
};
</script>

<style scoped>
.column-layout {
  display: flex;
  margin: 40px 20px 0 20px;
  justify-content: space-between;
}
.sidebars {
  width: 30%;
  padding: 20px;
  box-sizing: border-box;
  -webkit-box-shadow: 8px 10px 10px 0px rgba(112, 112, 112, 1);
  -moz-box-shadow: 8px 10px 10px 0px rgba(112, 112, 112, 1);
  box-shadow: 8px 10px 10px 0px rgba(112, 112, 112, 1);
}

.sidebars:nth-child(1) {
  background-color: rgba(177, 83, 78, 0.1);
}
.sidebars:nth-child(2) {
  background-color: rgba(177, 83, 78, 0.1);
}
.sidebars:nth-child(3) {
  background-color: rgba(177, 83, 78, 0.1);
}

ul {
  float: right;
  color: #172557;
  list-style-type: none;
}
h4 {
  margin-top: 5px;
  text-align: center;
}

/* Vue Animation  */
.fade-enter {
  opacity: 0.8;
}
.fade-enter-active {
  transition: opacity 1s;
}
.fade-leave {
  opacity: 1;
}
.fade-leave-active {
  transition: opacity 1s;
  opacity: 0.2;
}
</style>