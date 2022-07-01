<template>
  <form @submit.prevent="onSubmit">
    <h3>Enter details</h3>
    <label for="name">Name:</label>
    <input id="name" v-model="name" />
    <br />
    <label for="address">Address:</label>
    <textarea id="address" v-model="address"></textarea>
    <br />
    <label for="pan">Pan Number:</label>
    <input id="pan" v-model="pan" />
    <br />
    <input class="button" type="submit" value="Sign-up" />
  </form>
  <p v-for="(detail, index) in details" :key="index">
    {{ detail.name }} stays at {{ detail.address }} and has pan number {{ detail.pan }}
  </p>
</template>
<script>
export default {
  data() {
    return {
      name: "",
      address: "",
      pan: "",
      details: [],
    };
  },
  methods: {
    onSubmit() {
      if (this.name == "" || this.address == "" || this.pan == "") {
        alert("Enter all details.");
        return;
      }
      let detail = {
        name: this.name,
        address: this.address,
        pan: this.pan,
      };
      this.details.push(detail);
      this.name = "";
      this.address = "";
      this.pan = "";
    },
  },
};
</script>
