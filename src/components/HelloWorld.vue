<template>
  <div>
    <h3>Greetings Of The Day, {{ name }}</h3>
    <input v-model="name" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: "Ayush",
    };
  },
};
</script>
