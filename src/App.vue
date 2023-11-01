<script setup>
import { ref } from 'vue';

let qty = ref(0)
function addValue(){
  qty.value++
  console.log(qty)
}
function restValue(){
  if(qty.value>0){
  qty.value--
  console.log(qty)
}
}
</script>

<template>
  <section class="wrapper">
    <div class="profile">
      <div class="ballon" v-show="qty>0">{{qty}}</div>
    </div>

    <div class="button-wrapper">
      <div class="button" @click="restValue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>
    <div v-if="qty>0">me escribieron 😜</div>
    <div v-else>nadie me escribe 😒</div>
    <div v-else="qty>10">Uy apa estas solicitado 😃</div>

  </section>
  
</template>

<style scoped>
.button {
  background-color: #176e6a;
  display: inline-block;
  padding: 4px 0;
  border-radius: 4px;
  width: 32px;
  margin: 0 8px;
}

.button-wrapper {
  text-align: center;
  margin-top: 16px;
  margin-bottom: 16px;
}

.button:hover {
  cursor: pointer;
  background-color: #486966;
}

.ballon {
  position: absolute;
  top: 0;
  right: 0;
  width: 32px;
  height: 32px;
  background-color: #bd2a2e;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}

.profile {
  background-image: url(https://www.elnacional.cat/uploads/s1/44/37/78/27/leo-messi-balon-de-oro-2023-foto-efe.jpeg);
  background-size: cover;
  position: relative;

  width: 160px;
  height: 160px;
  margin: 0 auto;
  border-radius: 100%;
}

.wrapper {
  overflow: hidden;
  padding-top: 18px;
  background-color: #b2bebf;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
}
</style>
