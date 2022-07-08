<template></template>
<script>
import p1 from "./parent1.vue";
export default {
  mounted() {
    /*console.log("x");
    this.$root.$on("display", (like) => {
      log("xyz");
    });*/
  },
  methods: {
    display(liked) {
      for (let post in liked) {
        console.log(liked[post]);
      }
    },
  },
  components: {
    p1,
  },
};
</script>
