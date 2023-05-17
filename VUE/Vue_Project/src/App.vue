<script setup>
import { ref } from 'vue';

  const notify = ref(0);
  const title = ref("Juan David")

  function increase(){
    notify.value++;
  }

  function decrease(){
    if (notify.value>0) {
      notify.value--;
    } 
  }
</script>

<template>

  <h1>
    {{ title }}
  </h1>

  <div class="user">

    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
    <path stroke-linecap="round" stroke-linejoin="round" d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" />
    </svg>

    <div class="notification" v-if="notify != 0" >{{ notify }}</div>

  </div> <br>
  <div>
    <span @click="increase">
      +
    </span>

    <span @click="decrease">
      -
    </span>
  </div>

  <input type="text" v-model="title">
  
</template>

<style scoped>
.user {
  width:80px;
  height:80px;
  color:peru;
  position: relative;
}
.notification{
  background-color: red;
  color: white;
  border: 2px solid;
  border-radius: 20px;
  width: 28px;
  height: 28px;
  text-align: center;
  font-weight: bold;
  position: absolute; 
  top: 0px;
  right: 0px;
  border-color: rgb(81, 25, 25);
  
}
span {
  background-color: orange;
  display: inline-block;
  width: 24px;
  height: 24px;
  text-align: center;
  margin-right: 35px;
  border-radius: 4px;
  font-weight: bold;
}
span:hover {
  background-color: rgb(223, 147, 7);
  cursor: pointer;
}
</style>
