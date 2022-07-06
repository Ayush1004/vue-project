<template>
  <div>
    <div v-for="post in posts">
      <h4>{{ post.name }}</h4>
      <h4>{{ post.image }}</h4>
      <p>{{ post.desc }}</p>
      <p>{{ post.date }}</p>
      <button v-on:click="addP(post)">Like</button>
      <p>{{ post.count }}</p>
    </div>
  </div>
  <p>{{ like }}</p>
</template>
<script>
export default {
  data() {
    return {
      posts: [
        {
          name: "Food",
          desc: "Italian dish",
          image: "pasta",
          date: "24-05-2022",
          count: 0,
        },
        {
          name: "Food",
          desc: "Italian dish",
          image: "pizza",
          date: "20-05-2022",
          count: 5,
        },
        {
          name: "Food",
          desc: "Italian dish",
          image: "ravioli",
          date: "24-05-2022",
          count: 3,
        },
      ],
      like: [],
    };
  },
  methods: {
    addP(post) {
      post.count += 1;
      //console.log(this.like);
      //console.log(post.count);
      this.like.push(post);
      this.$emit("likedpost", this.like);
    },
  },
};
</script>
