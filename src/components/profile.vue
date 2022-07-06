<template>
  <label for="name">Enter Name: </label>
  <input type="text" v-model="name" id="name" @input="callingm" />
</template>
<script>
export default {
  data() {
    return {
      name: "",
    };
  },
  methods: {
    callingm() {
      this.$emit("name", this.name);
    },
  },
};
</script>
