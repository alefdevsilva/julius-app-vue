<template>
  <div>
    <MarcaJulius />
    <HeaderJulius />
  </div>
</template>

<script setup>
import HeaderJulius from './components/HeaderJulius.vue';
import MarcaJulius from './components/MarcaJulius.vue'
</script>

<style>
@font-face {
  font-family: "padrao";
  src: url(./fonts/KumbhSans-Regular.ttf);
}

@font-face {
  font-family: "negrito";
  src: url(./fonts/KumbhSans-Bold.ttf);
}

:root {
  --cor-destaque: #5333ed;
}

body{
  margin: 0;
  background-color: #dddddd;
}
</style>
