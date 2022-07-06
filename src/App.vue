<template>
  <display></display>
</template>

<script>
//import parent from "./components/parent.vue";
//import pro from "./components/products.vue";
//import p6 from "./components/input.vue";
//import emp from "./components/EmployeeForm.vue";
//import temp from "./components/temp.vue";
//import log from "./components/loginform.vue";
//import temp from "./components/temp1.vue";
import p1 from "./components/parent1.vue";
import display from "./components/desc.vue";
export default {
  data() {},
  /*mounted() {
    console.log("x");
    this.$root.$once("display", (like) => {
      console.log("xyz");
    });
  },*/
  components: {
    p1,
    display,
  },
};
</script>
