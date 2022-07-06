<template>
  <div>
    <h3>Welcome {{ name }}</h3>
  </div>
</template>
<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
      default: "",
    },
  },
};
</script>
