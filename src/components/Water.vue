<!--<script setup>
import { ref } from 'vue';
import GlassFilledIcon from '../components/icons/GlassFilledIcon.vue';

    let /*waterAmount*/ ilosc= ref(0);
    let /*glassNum*/ iloscKubkow = 5;

    function updateAmount(iloscKubkow){ 
        //waterAmount += 250;
        console.log("waterAmount=",glassesAmount);
        this.ilosc = iloscKubkow * 250;
    }
</script>

<template>
    <div class="glass-space">
        <div v-for="ilosc in iloscKubkow" :key="iloscKubkow" @click="updateAmount(iloscKubkow)">
            <GlassFilledIcon/>
        </div>

        <p>Ilość wypitej wody: {{ ilosc }}</p>

        !-- <h2>Component do monitorowania wody</h2>
        
        <div @click="fillGlass" v-for="i in 8" class="glasses">
            <GlassFilledIcon></GlassFilledIcon>
        </div>   
        
        <h4>Ilość wody dzisiaj: {{ waterAmount }} ml</h4> --
    </div>
    
</template>

<style lang="scss" scoped>
    .glass-space{
        border: 2px dotted black;
        background-color: lightgray;
        
        div{
            display: inline-flex;
        }
    }
</style>-->




<script>
import { ref } from 'vue';
import GlassFilledIcon from '../components/icons/GlassFilledIcon.vue';

export default {
  data() {
    return {
      iloscKubkow: 5, // Możesz dostosować ilość kubków według potrzeb
      ilosc: 0
    };
  },
  methods: {
    zaktualizujIlosc(numer_kubka) {
      this.ilosc = numer_kubka * 250;
    }
  }
};
</script>

<template>
  <div>
    <div v-for="numer_kubka in iloscKubkow" :key="numer_kubka" @click="zaktualizujIlosc(numer_kubka)">
      <img src="sciezka_do_obrazka_kubka.png" alt="Kubek jcnrnenvkjrvernvkjrnkvj"/>
    </div>
    <p>Aktualna ilość: {{ ilosc }}</p>
  </div>
</template>


