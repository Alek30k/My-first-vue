<script setup>
import { ref, computed } from "vue";
const name = "Vue dinámico";
const styleColor = "color: blue";
// const arrayFrutas = ["🍎", "🍏", "🍍", "🍎", "🍏", "🍍"];

// const arrayFrutas = [
//   {
//     name: "Manzana",
//     price: "$1.00",
//     desc: "Una manzana",
//   },
//   {
//     name: "Pera",
//     price: "$2.00",
//     desc: "Una pera",
//   },
//   {
//     name: "Naranja",
//     price: "$3.00",
//     desc: "Una naranja",
//   },
// ];

//método - methods

// const handleClick = (e) => {
//   console.log(e);
// };

const counter = ref(0);

const increment = () => {
  counter.value++;
};
const decrement = () => {
  counter.value--;
};
const reset = () => {
  counter.value = 0;
};
const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  } else if (counter.value < 0) {
    return "negative";
  } else {
    return "positive";
  }
});
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">Soy azul</h2>
  <!-- <ul>
    <li v-for="fruta in arrayFrutas" :key="fruta.name">
      {{ fruta.name }} - {{ fruta.price }} - {{ fruta.desc }}
    </li>
  </ul> -->

  <!-- <button @click.left="handleClick('text Left')">Activame left</button>
  <button v-on:click.right.prevent="handleClick('text Right')">
    Activame right
  </button>
  <button v-on:click.middle="handleClick('text Middle')">
    Activame middle
  </button> -->

  <h2 :class="classCounter">{{ counter }}</h2>
  <button @click="increment">increment</button>
  <button @click="decrement">decrement</button>
  <button @click="reset">Reset</button>
</template>

<style>
h1 {
  color: blueviolet;
}

.zero {
  color: peru;
}
.positive {
  color: green;
}
.negative {
  color: red;
}
</style>
