<template>
  <div>
    <label for="x">Enter Length: </label>
    <input id="x" v-model.number="x" /><br />

    <label for="y">Enter Breadth: </label>
    <input id="y" v-model.number="y" /><br />

    <button v-on:click="carea">Calculate Area</button>
    <h3 v-if="area">Area: {{ area }}</h3>
  </div>
</template>
<script>
export default {
  data() {
    return {
      x: 0,
      y: 0,
      area: 0,
    };
  },
  methods: {
    carea() {
      this.area = this.x * this.y;
    },
  },
};
</script>
