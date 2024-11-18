<template>
  <div id="app">
    <div class="grid-container">
      <CosineLaw />
      <AsymptoteFinder />
      <GregoryLeibnizPi />
    </div>
  </div>
</template>

<script>
import CosineLaw from './components/CosineLaw.vue';  
import AsymptoteFinder from './components/AsymptoteFinder.vue'; 
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue'; 

export default {
  components: {
    CosineLaw,
    AsymptoteFinder,
    GregoryLeibnizPi
  }
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(600px, 1fr));  
  gap: 30px;  
  width: 100%; 
  max-width: 1800px; 
  margin: 0 auto;  
  padding: 20px;  
}

.grid-container > * {
  margin-bottom: 15px;  
  width: 100%;  
  padding: 30px;  
  box-sizing: border-box;  
  background-color: white; 
  border-radius: 15px;  
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);  
}

.grid-container > :first-child {
  margin-right: 50px; 
}

@media (max-width: 768px) {
  .grid-container {
    grid-template-columns: 1fr;  
    gap: 30px;  
  }
}

@media (min-width: 1200px) {
  .grid-container {
    grid-template-columns: repeat(2, 1fr);  
    gap: 40px;  
  }
  .grid-container > * {
    max-width: 1200px;  
  }
}

@media (min-width: 1800px) {
  .grid-container {
    grid-template-columns: repeat(2, 1fr); 
    gap: 50px;  
  }
  .grid-container > * {
    max-width: 1500px;  
  }
}
</style>
