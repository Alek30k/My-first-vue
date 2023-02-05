<script setup>
const name = "Vue dinámico";
const styleColor = "color: blue";
// const arrayFrutas = ["🍎", "🍏", "🍍", "🍎", "🍏", "🍍"];
const arrayFrutas = [
  {
    name: "Manzana",
    price: "$1.00",
    desc: "Una manzana",
  },
  {
    name: "Pera",
    price: "$2.00",
    desc: "Una pera",
  },
  {
    name: "Naranja",
    price: "$3.00",
    desc: "Una naranja",
  },
];
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">Soy azul</h2>
  <ul>
    <li v-for="fruta in arrayFrutas" :key="fruta.name">
      {{ fruta.name }} - {{ fruta.price }} - {{ fruta.desc }}
    </li>
  </ul>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
