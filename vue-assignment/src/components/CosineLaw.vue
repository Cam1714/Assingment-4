<template>
  <div id="CosineLaw" class="dform">
    <h2 class="header">Cosine Law</h2>
    <form @submit.prevent="cosineLaw">
      <label for="sideA">Side A:</label><br>
      <input class="number" id="sideA" v-model.number="sideA" type="number" required /><br>

      <label for="sideB">Side B:</label><br>
      <input class="number" id="sideB" v-model.number="sideB" type="number" required /><br>

      <label for="angleC">Angle C (in degrees):</label><br>
      <input class="number" id="angleC" v-model.number="angleC" type="number" required /><br>

      <label for="sideC">Side C (Result):</label><br>
      <input class="number" id="sideC" v-model="sideC" readonly /><br>

      <button class="Calculate" type="submit">Calculate</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sideA: null,
      sideB: null,
      angleC: null,
      sideC: null,
    };
  },
  methods: {
    cosineLaw() {
      if (isNaN(this.sideA) || isNaN(this.sideB) || isNaN(this.angleC)) {
        alert("Please enter valid numbers for Side A, Side B, and Angle C.");
        return;
      }

      const angleCRadians = this.angleC * (Math.PI / 180);
      this.sideC = Math.sqrt(Math.pow(this.sideA, 2) + Math.pow(this.sideB, 2) - 2 * this.sideA * this.sideB * Math.cos(angleCRadians)).toFixed(2);
    }
  }
};
</script>


