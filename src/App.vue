<template>
  <div>
    <MarcaJulius />
    <HeaderJulius />

    <div id="container">
      <PainelLancamentos />
      <PainelResumo />
    </div>
  </div>
</template>

<script setup>
import HeaderJulius from './components/HeaderJulius.vue';
import MarcaJulius from './components/MarcaJulius.vue'
import PainelLancamentos from './components/PainelLancamentos.vue';
import PainelResumo from './components/PainelResumo.vue';
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

#container {
  display: flex;
  padding: 20px;
}

</style>
