<script setup>
  import { ref } from 'vue';

  const valBoleto = 5000;

  let cant = 0;
  let total = ref(0);
  let descuento = 0.5;

  function comprar() {
    if(cant>5) {
      total.value = (+cant*valBoleto);
      total.value = total.value - (total.value*descuento);
    } else {
      total.value = +cant*valBoleto;
    }
  }
</script>

<template>
  <div class=" h-screen w-screen bg-blue-500 flex justify-center items-center">
    <div class=" m-auto bg-blue-200 h-3/5 w-1/3 shadow-green-300 rounded-md border-4 shadow-2xl">
      <div class=" bg-transparent h-full w-2/3 m-auto pt-8">
        <label for="entradas">
          Cantidad
        </label>
        <input type="number" id="entradas" name="entradas" class=" ml-4 px-3 h-12 rounded-sm outline-none"
        v-model="cant" @keydown.enter="comprar()">

        <p class="text-center mt-7 text-xl font-semibold">
          Valor a Pagar: {{ total }}
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
