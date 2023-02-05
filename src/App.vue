<script setup>
const name = "Vue dinámico";
const styleColor = "color: blue";
const arrayFrutas = ["🍎", "🍏", "🍍", "🍎", "🍏", "🍍"];
</script>

<template>
  <h1>Hello {{ name.toUpperCase() }}</h1>
  <h2 :style="styleColor">Soy azul</h2>
  <ul>
    <li v-for="(fruta, i) in arrayFrutas">{{ i }} - {{ fruta }}</li>
  </ul>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
