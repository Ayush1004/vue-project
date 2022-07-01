<template>
  <div>
    <label for="uname">Username:</label>
    <input id="uname" v-model="uname" />
    <br />
    <label for="pwd">Password:</label>
    <input type="password" id="pwd" v-model="pwd" />
    <br />
    <button v-on:click="confirm">Log-In</button>
    <h4 v-if="req">Login successfully</h4>
  </div>
</template>
<script>
export default {
  data() {
    return {
      uname: "",
      pwd: "",
      req: false,
    };
  },
  methods: {
    confirm() {
      if (this.uname == "admin" && this.pwd == "admin") {
        this.req = true;
        this.uname = "";
        this.pwd = "";
      } else {
        alert("Enter correct username or password");
      }
    },
  },
};
</script>
