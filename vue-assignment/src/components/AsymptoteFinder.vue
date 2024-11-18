<template>
  <div id="Asymptote" class="dform">
    <h2 class="header">Asymptote Finder</h2>
    <form @submit.prevent="asymptoteFinder">
      <label for="mvalue">m Value:</label><br>
      <input class="number" id="mvalue" v-model.number="mvalue" type="number" /><br>

      <label for="nvalue">n Value:</label><br>
      <input class="number" id="nvalue" v-model.number="nvalue" type="number" /><br>

      <label for="atype">Asymptote Type (Result):</label><br>
      <input class="number" id="atype" v-model="atype" readonly /><br>

      <button class="Calculate" type="submit">Calculate</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mvalue: null,
      nvalue: null,
      atype: "",
    };
  },
  methods: {
    asymptoteFinder() {
      if (isNaN(this.mvalue) || isNaN(this.nvalue)) {
        alert("Please enter valid numbers for m Value and n Value.");
        return;
      }

      let output = "";

      if (this.mvalue === this.nvalue) {
        output = "The asymptote is horizontal";
      } else if (this.nvalue > this.mvalue) {
        output = "The asymptote is the x-axis";
      } else if (this.mvalue > this.nvalue) {
        const difference = this.mvalue - this.nvalue;
        switch (difference) {
          case 1: output = "Linear"; break;
          case 2: output = "Quadratic"; break;
          case 3: output = "Cubic"; break;
          case 4: output = "Quartic"; break;
          case 5: output = "Quintic"; break;
          case 6: output = "Sextic"; break;
          case 7: output = "Septic"; break;
          case 8: output = "Octic"; break;
          case 9: output = "Nonic"; break;
          case 10: output = "Decic"; break;
          default: output = "Undefined"; break;
        }
      }

      this.atype = output;
    }
  }
};
</script>


