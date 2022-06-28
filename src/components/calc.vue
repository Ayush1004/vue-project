<template>
  <div>
    <label for="x">Enter first number:</label>
    <input id="x" v-model.number="x" /><br />

    <label for="y">Enter first number:</label>
    <input id="y" v-model.number="y" /><br />

    <button v-on:click="addition">Addition</button>
    <button v-on:click="sub">Subtraction</button>
    <button v-on:click="multiply">Multiplication</button>
    <h3 v-if="ans">Result: {{ ans }}</h3>
  </div>
</template>
<script>
export default {
  data() {
    return {
      x: null,
      y: null,
      ans: 0,
    };
  },
  methods: {
    addition() {
      this.ans = this.x + this.y;
    },
    sub() {
      this.ans = this.x - this.y;
    },
    multiply() {
      this.ans = this.x * this.y;
    },
  },
};
</script>
<style>
input {
  width: 100px;
  height: 20px;
}
button {
  width: 100px;
  height: 20px;
  margin-right: 5px;
}
</style>
