<template>
  <div id="Gregory-Leibniz" class="dform">
    <h2 class="header">Gregory-Leibniz Pi Approximation</h2>
    <form @submit.prevent="piApprox">
      <!-- Using v-model for data binding -->
      <label for="nvalue">n Value:</label><br>
      <input class="number" id="Nvalue" v-model.number="nvalue" type="number" /><br>

      <label for="piapprox">Pi Approximation (Result):</label><br>
      <input class="number" id="piapprox" v-model="piapprox" readonly /><br>

      <!-- Using @click to bind the method to the button -->
      <button class="Calculate" type="submit">Calculate</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nvalue: null,    // To store the input value for 'n'
      piapprox: "",    // To store the result for Pi approximation
    };
  },
  methods: {
    piApprox() {
      let pi = 0;
      const n = this.nvalue;  // Get the 'n' value from the data

      if (isNaN(n)) {
        alert("Please enter a valid number for n Value.");
        return;
      }

      // Gregory-Leibniz series calculation
      for (let i = 0; i <= n; i++) {
        pi += (Math.pow(-1, i)) / ((2 * i) + 1);
      }

      pi = pi * 4; // Multiply by 4 to get Pi approximation
      this.piapprox = pi.toFixed(6); // Set the result in piapprox
    }
  }
};
</script>