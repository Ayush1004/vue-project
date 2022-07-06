<template>
  <post @likedpost="postmethod"></post>
  <button v-if="liked.length" v-on:click="send()">{{ liked.length }}</button>
</template>
<script>
import post from "./postlist.vue";
export default {
  data() {
    return {
      liked: [],
    };
  },
  methods: {
    postmethod(post) {
      this.liked = post;
    },
    send() {
      console.log("add");
      this.$root.$emit("display", 0);
    },
  },
  components: {
    post,
  },
};
</script>
