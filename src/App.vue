<script setup>
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

const handleClick = (e) => {
  console.log(e);
};
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">Soy azul</h2>
  <!-- <ul>
    <li v-for="fruta in arrayFrutas" :key="fruta.name">
      {{ fruta.name }} - {{ fruta.price }} - {{ fruta.desc }}
    </li>
  </ul> -->

  <button @click.left="handleClick('text Left')">Activame left</button>
  <button v-on:click.right="handleClick('text Right')">Activame right</button>
  <button v-on:click.middle="handleClick('text Middle')">
    Activame middle
  </button>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
