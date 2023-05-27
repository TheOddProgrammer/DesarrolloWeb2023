<script setup>
  import { ref, computed } from 'vue';

  let Naranjas = ref(0);
  const precioNaranjas = 500;
  let Manzanas = ref(0);
  const precioManzanas = 300;
  let Bananas = ref(0);
  const precioBananas = 600;
  let Total = ref(0);
  let Pagar = ref(0);

  function increaseNaranjas() {
    Naranjas.value++;
    total();
    pagar();
  }
  function decreaseNaranjas() {
    if (Naranjas.value > 0) {
      Naranjas.value--;
      total();
      pagar();
    }
  }
  function increaseBananas() {
    Bananas.value++;
    total();
  }
  function decreaseBananas() {
    if (Bananas.value > 0) {
      Bananas.value--;
      total();
    }
  }
  function increaseManzanas() {
    Manzanas.value++;
    total();
  }
  function decreaseManzanas() {
    if (Manzanas.value > 0) {
      Manzanas.value--;
    }
  }
  function total() {
    Total.value = Manzanas.value + Bananas.value + Naranjas.value;
    pagar();
  }
  function limpiar() {
    Manzanas.value = 0;
    Naranjas.value = 0;
    Bananas.value = 0;
    Total.value = 0;
    Pagar.value = 0;
  }
  function pagar() {
    Pagar.value = (Naranjas.value*precioNaranjas) + (Manzanas.value*precioManzanas) + (Bananas.value*precioBananas);
  }

  const iva = computed(() => {
    return Pagar.value > 0 ? (Pagar.value+(Pagar.value*0.2)) : Pagar.value;
  })
</script>

<template>
  <h1>
    Preparacion Parcial N°1
  </h1>

  <div class="Productos">
    <h2>
      Naranjas Cantidad: {{ Naranjas }}
    </h2>
    <span @click="increaseNaranjas">
      +
    </span>
    <span @click="decreaseNaranjas">
      -
    </span>
  </div>

  <div class="Productos">
    <h2>
      Bananos Cantidad: {{ Bananas }}
    </h2>
    <span @click="increaseBananas">
      +
    </span>
    <span @click="decreaseBananas">
      -
    </span>
  </div>

  <div class="Productos">
    <h2>
      Manzanas Cantidad {{ Manzanas }}
    </h2>
    <span @click="increaseManzanas">
      +
    </span>
    <span @click="decreaseManzanas">
      -
    </span>
  </div>

  <h2>Total {{ Total }} Productos</h2>
  <h2>Paga Total: {{ Pagar }}</h2>
  <h2>Total Con IVA: {{ iva }}</h2>

  <button v-if="Total>0" @click="limpiar">Clean</button>
</template>

<style scoped>
  h1 {
    font-weight: bold;
    color: red;
    font-size:medium;
  }

  h2 {
    font-size: small;
  }

  span {
    height: 25px;
    width: 30px;
    background-color: green;
    margin: 10px;
    text-align: center;
    padding: 0 10px 0 10px;
  }

  span:hover {
    cursor: pointer;
  }

  .Productos {
    text-align: center;
  }
</style>
