<script setup>
  import { ref } from 'vue';

  let cl = ref(0);
  let cd = ref(0);
  let likes = ref(93);
  let dislikes = ref(5);

  function increase() {
    if (cl.value<1) {
      likes.value++;
      cl.value++;
    }else if(cl.value==1) {
      likes.value--;
      cl.value--;
    }
  }

  function decrease() {
    if(cd.value<1){
      dislikes.value++;
      cd.value++;
    } else if(cd.value>=1 && cd.value>0) {
      dislikes.value--;
      cd.value--;
    }
  }
</script>

<template>
  <div class=" w-screen h-screen bg-green-200 flex select-none">
    <div class=" m-auto h-[90%] w-1/3 bg-white shadow-lg shadow-green-500 rounded-xl py-8 px-4">
      <div class=" h-10 flex justify-between items-center px-3">
        <h1 class=" font-bold font-serif text-gray-600">Historias</h1>
        <button class=" bg-blue-500 w-14 rounded text-white hover:bg-gray-400 hover:text-blue-500 hover:font-bold">Todas</button>
      </div>
      <div class="flex h-40 mt-2 p-3 justify-between  ">
        <div class=" h-full text-center">
          <div class=" h-[70%] w-full">
            <img src="../public/Persona 1.jpg" alt="Persona 1" class="hover:cursor-pointer h-full w-full mb-2 rounded-xl border-4 border-blue-400">
            <div class=" text-left pl-1 text-gray-500 text-sm">Mariana</div>
          </div>
        </div>

        <div class=" h-full text-center">
          <div class=" h-[70%] w-full">
            <img src="../public/Rick.jpg" alt="Persona 2" class="hover:cursor-pointer h-full w-full mb-2 rounded-xl border-4 border-gray-400">
            <div class=" text-left pl-1 text-gray-500 text-sm">Ricky</div>
          </div>
        </div>

        <div class=" h-full text-center">
          <div class=" h-[70%] w-full">
            <img src="../public/Persona 3.jpg" alt="Persona 3" class="hover:cursor-pointer h-full w-full mb-2 rounded-xl border-4 border-blue-400">
            <div class=" text-left pl-1 text-gray-500 text-sm">Felipe Sesamo</div>
          </div>
        </div>

        <div class=" h-full text-center">
          <div class=" h-[70%] w-full">
            <img src="../public/barney.jpg" alt="Cachorrito" class="hover:cursor-pointer h-full w-full mb-2 rounded-xl border-4 border-gray-400">
            <div class=" text-left pl-1 text-gray-500 text-sm">Barney Dino</div>
          </div>
        </div>
      </div>

      <div class="h-1/2  w-full">

        <div class="h-16  p-2 flex">
          <div class=" w-1/2  h-full flex">
            <div class=" h-full rounded-full">
              <img src="../public/Andres.jpg" alt="Cachorrito" class="hover:cursor-pointer h-full rounded-full full">
            </div>
            <div class=" ml-4 mt-1">
              <p class="font-bold hover:cursor-pointer">
                <a href="https://twitter.com/AndresPastrana_" target="_blank">Andrés Pastrana</a>
              </p>
              <span class=" font-light text-gray-700 text-sm">
                Hace 10 Minutos
              </span>
            </div>
          </div>

          <div class=" w-1/2  h-full flex items-end justify-end p-1 italic">
            <p class="text-red-500 font-semibold hover:cursor-pointer hover:text-red-700">Reportar</p>
          </div>

        </div>

        <div class=" m-3">
          <div class="h-full w-full flex justify-center">
            <img src="../public/fiesta.jpg" alt="fiesta" class=" h-[320px] rounded-3xl">
          </div>
        </div>

      </div>

      <!-- HERE -->

      <div class=" h-10 w-full px-8 flex"> 
        <div class=" flex h-full w-16 items-center mr-3">
          <div class="">
            <svg xmlns="http://www.w3.org/2000/svg" fill="white" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-red-600 hover:cursor-pointer rounded-sm  hover:bg-red-400" @click="increase()" v-if="cl==0">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
            </svg>

            <svg xmlns="http://www.w3.org/2000/svg" fill="red" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-red-600 hover:cursor-pointer rounded-sm  hover:bg-red-400" @click="increase()" v-if="cl==1">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
            </svg>
          </div>

          <div class="ml-3 text-xl text-gray-500">
            {{ likes }}
          </div>
        </div>

        <div class="flex h-full w-16 items-center">
          <div class="">
            <svg xmlns="http://www.w3.org/2000/svg" fill="white" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-blue-600 hover:cursor-pointer rounded-sm hover:bg-blue-400" @click="decrease()" v-if="cd==0">
            <path stroke-linecap="round" stroke-linejoin="round" d="M7.5 15h2.25m8.024-9.75c.011.05.028.1.052.148.591 1.2.924 2.55.924 3.977a8.96 8.96 0 01-.999 4.125m.023-8.25c-.076-.365.183-.75.575-.75h.908c.889 0 1.713.518 1.972 1.368.339 1.11.521 2.287.521 3.507 0 1.553-.295 3.036-.831 4.398C20.613 14.547 19.833 15 19 15h-1.053c-.472 0-.745-.556-.5-.96a8.95 8.95 0 00.303-.54m.023-8.25H16.48a4.5 4.5 0 01-1.423-.23l-3.114-1.04a4.5 4.5 0 00-1.423-.23H6.504c-.618 0-1.217.247-1.605.729A11.95 11.95 0 002.25 12c0 .434.023.863.068 1.285C2.427 14.306 3.346 15 4.372 15h3.126c.618 0 .991.724.725 1.282A7.471 7.471 0 007.5 19.5a2.25 2.25 0 002.25 2.25.75.75 0 00.75-.75v-.633c0-.573.11-1.14.322-1.672.304-.76.93-1.33 1.653-1.715a9.04 9.04 0 002.86-2.4c.498-.634 1.226-1.08 2.032-1.08h.384" />
            </svg>

            <svg xmlns="http://www.w3.org/2000/svg" fill="blue" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-blue-600 hover:cursor-pointer rounded-sm hover:bg-blue-400" @click="decrease()" v-if="cd==1">
            <path stroke-linecap="round" stroke-linejoin="round" d="M7.5 15h2.25m8.024-9.75c.011.05.028.1.052.148.591 1.2.924 2.55.924 3.977a8.96 8.96 0 01-.999 4.125m.023-8.25c-.076-.365.183-.75.575-.75h.908c.889 0 1.713.518 1.972 1.368.339 1.11.521 2.287.521 3.507 0 1.553-.295 3.036-.831 4.398C20.613 14.547 19.833 15 19 15h-1.053c-.472 0-.745-.556-.5-.96a8.95 8.95 0 00.303-.54m.023-8.25H16.48a4.5 4.5 0 01-1.423-.23l-3.114-1.04a4.5 4.5 0 00-1.423-.23H6.504c-.618 0-1.217.247-1.605.729A11.95 11.95 0 002.25 12c0 .434.023.863.068 1.285C2.427 14.306 3.346 15 4.372 15h3.126c.618 0 .991.724.725 1.282A7.471 7.471 0 007.5 19.5a2.25 2.25 0 002.25 2.25.75.75 0 00.75-.75v-.633c0-.573.11-1.14.322-1.672.304-.76.93-1.33 1.653-1.715a9.04 9.04 0 002.86-2.4c.498-.634 1.226-1.08 2.032-1.08h.384" />
            </svg>
          </div>
          <div class="ml-3 text-xl text-gray-500">
            {{ dislikes }}
          </div>
        </div>
      </div>

      <div class=" h-36 mt-2 w-full hover:cursor-pointer flex items-center justify-center">
        <div class=" bg-gray-300 h-[50%] w-[80%] rounded-xl p-2 flex justify-between items-center px-28 shadow-lg shadow-gray-400">
          <div class=" hover:bg-white rounded-md h-14 w-14 flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="hover:w-8 hover:h-8 w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z" />
            </svg>
          </div>
          
          <div class=" hover:bg-white hover:cursor-pointer rounded-md h-14 w-14 flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hover:w-8 hover:h-8">
            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
            </svg>
          </div>

          <div class=" hover:bg-white hover:cursor-pointer rounded-md h-14 w-14 flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hover:w-8 hover:h-8">
            <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" />
            </svg>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>

</style>