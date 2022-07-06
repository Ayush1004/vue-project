<template>
  <label for="name">Enter Name: </label>
  <input type="text" v-model="name" id="name" />
  <display v-if="name.length" :name="name"></display>
</template>
<script>
import display from "./display.vue";
export default {
  data() {
    return {
      name: "",
    };
  },
  components: {
    display,
  },
};
</script>
