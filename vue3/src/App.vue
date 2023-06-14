<script setup>
  import { ref } from 'vue';

  const valBoleto = 5000;

  let cant = 0;
  let precio = ref(0);
  let perDescuento = 0.25;

  function comprar() {
    if(cant>3) {
      precio.value = (+cant * valBoleto);
      precio.value = precio.value - (precio.value*perDescuento);
    } else {
      precio.value = +cant * valBoleto;
    }
  }


  //Jueguito

  let cubo = document.getElementById('cubito');

  function bajar() {
    cubo.style.top = '100px';
  }
  function subir() {
    cubo.style.marginTop = '100px';
  }
  function izq() {
    cubo.style.marginTop = '100px';
  }
  function derecha() {
    cubo.style.marginTop = '100px';
  }

</script>

<template>

  <div class="bg-slate-200 w-[400px] mx-auto py-4 px-6 rounded-md mt-36 shadow-md">
    
    <label for="entradas">
      Cantidad
    </label>

    <input type="number" id="entradas" name="entrafas" class="ml-4 px-2 h-8 rounded-sm outline-none" v-model="cant" @keydown.enter="comprar()">
    
    <button class=" bg-blue-300 px-2 ml-4 rounded-md hover:bg-blue-500 hover:text-white" 
    @click="comprar()">Buy</button>

    <p class="text-center mt-7 text-xl font-semibold">
    Valor a Pagar: {{ precio }}
    </p>
  </div>

  <div class="mx-auto mt-36 bg-green-300 rounded-md p-2 h-56 w-56 relative"> 
    <input class="bg-red-500 text-red-500 h-10 w-10 rounded-md absolute top-0 left-0" id="cubito"
    @keydown.up="subir()" @keydown.right="derecha()" @keydown.down="bajar()" @keydown.left="izq()">
  </div>
  
</template>

<style scoped>

</style>
