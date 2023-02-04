<script setup>
const name = "Vue dinámico";
const styleColor = "color: blue";
</script>

<template>
  <h1>Hello {{ name }}</h1>
  <h2 v-bind:style="styleColor">Soy azul</h2>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
