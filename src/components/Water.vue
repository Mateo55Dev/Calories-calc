<script setup>
import { ref } from 'vue';
import GlassFilledIcon from '../components/icons/GlassFilledIcon.vue';

const glassCapacity = 250;
var glassNum = 8;
var waterAmount = ref(0);

function updateWaterAmount(numer_kubka) {
  this.waterAmount = numer_kubka * glassCapacity;
  
  if (this.glassNum == numer_kubka) {
    this.glassNum += 1;
  }
}

function resetWaterAmount() {
    this.waterAmount = 0;
    this.glassNum = 8;
}
</script>

<template>
  <div class="glass-space">
    <div v-for="numer_kubka in glassNum" :key="numer_kubka" @click="updateWaterAmount(numer_kubka)">
      <GlassFilledIcon/>
    </div>
    <p>Aktualna ilość: {{ waterAmount + " ml"}}</p>
    <button @click="resetWaterAmount()">Wyczyść wodę</button>
  </div>
</template>

<style lang="scss" scoped>
    .glass-space{
        border: 2px dotted black;
        
        div{
            display: inline-flex;
            path#secondary{
                background: lightblue;
                transition: background 1s;
                fill: black; //nie działa
            }
        }
        p{
            font-size: 1.5em;
            font-style: bold;
        }
    }
</style>