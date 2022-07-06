<template>
  <productlist v-if="product.length" :product="product"></productlist>
</template>
<script>
import productlist from "./productlist.vue";
export default {
  data() {
    return {
      product: [
        { name: "Shoes", price: 1000, quantity: 5 },
        { name: "Bagpack", price: 800, quantity: 8 },
        { name: "Socks", price: 100, quantity: 12 },
        { name: "Wallet", price: 300, quantity: 3 },
        { name: "Belt", price: 200, quantity: 10 },
      ],
    };
  },
  components: {
    productlist,
  },
};
</script>
