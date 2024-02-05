<template>

<div v-if="!yesC" class="card">
  <img src="../src/assets/cardGif.gif">
  <div class="title">
    💙~ Will you be my valentines? ~💜
  </div>

  <div class="buttons">
    <button v-bind:style="{ fontSize: yesSize + 'px'}" @click="yesC = true" class="yes">Yes</button>
    <button v-bind:style="{ fontSize: 100 - counter * 10 + 'px' }" @click="incrementCounter()" class="no"> {{ arr[counter] }}</button>
  </div>
</div>
<div v-else>
  <img class="thing" src="../src/assets/yes.gif">
  <div class="title">YIPPIEEEEEEE</div>
</div>

</template>

<script setup>
import {ref} from 'vue'

const counter = ref(0);
const yesC = ref(false);
const yesSize = ref(100);
const arr = ["No","Are you sure?","Really?","U would do that to us?","I cant believe you rn","You cant be srs","ZONT","please?","pleaseee","PLEASEE"]

function incrementCounter(){
  if(counter.value == arr.length -1){
    counter.value = 0;
    yesSize.value = 100;
  }
  else{
  counter.value++
  yesSize.value = 100 + counter.value * 30
  
  }
}

</script>

<style>
body{
  background-color: rgb(250, 238, 236);
}
.card{
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
img{
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 33%;
}
.title{
  text-align: center;
  padding-top: 100px;
  font-size: 90px;
  font-family: 'Comic Neue', cursive;
}
.thing{
  width: 80%;
}
button{
  margin: 25px;
  padding: 15px;
  border-radius: 10px;
}
.yes{
  background-color: lightgreen;
}
.no{
  background-color: lightcoral;
}
.buttons{
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
