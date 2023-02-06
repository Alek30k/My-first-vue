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
const ArrayFavorite = ref([]);

const increment = () => {
  counter.value++;
};
const decrement = () => {
  counter.value--;
};
const reset = () => {
  counter.value = 0;
  ArrayFavorite.value = [];
};
const add = () => {
  ArrayFavorite.value.push(counter.value);
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

const blockNumber = computed(() => {
  const numSearch = ArrayFavorite.value.find((num) => num === counter.value);
  //   if (numSearch === 0) return true;
  //   return numSearch ? true : false;
  //
  return numSearch || numSearch === 0;
});
</script>

<template>
  <div class="container text-center">
    <h1>Hello {{ name.toUpperCase() }}</h1>
    <h2 :style="styleColor">Soy azul</h2>
    <br />
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
    <div class="btn-group">
      <button @click="increment" class="btn btn-success">increment</button>
      <button @click="decrement" class="btn btn-danger">decement</button>
      <button @click="reset" class="btn btn-secondary">Reset</button>
      <button @click="add" :disabled="blockNumber" class="btn btn-primary">
        Add
      </button>
    </div>

    <ul class="list-group mt-4">
      <li
        v-for="(num, index) in ArrayFavorite"
        :key="index"
        class="list-group-item"
      >
        {{ num }}
      </li>
    </ul>
  </div>
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
