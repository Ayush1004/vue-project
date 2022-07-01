<template>
  <signup @details="adddetail"></signup>
</template>
<script>
import signup from "./signup.vue";
export default {
  data() {
    return {
      details: [],
    };
  },
  methods: {
    adddetail(detail) {
      this.details.push(detail);
    },
  },
  components: {
    signup,
  },
};
</script>
