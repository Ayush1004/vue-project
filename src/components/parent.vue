<template>
  <div>
    <profile @name="print" id="1"></profile>
    <h3 id="1"></h3>
  </div>
</template>
<script>
import profile from "./profile.vue";
export default {
  methods: {
    print(name) {
      console.log(name);
      document.getElementById("1").innerHTML = "Name: " + name;
    },
  },
  components: {
    profile,
  },
};
</script>
