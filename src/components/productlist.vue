<template>
  <div>
    <h3>Products:</h3>
    <ul v-for="(p, i) in product" :key="i">
      <li>
        Product Name: {{ p.name }} <br />
        Product price: {{ p.price }} <br />
        Quantity available: {{ p.quantity }} <br />Discount: 5% <br />
        Payable Price: {{ parseInt(0.95 * p.price) }} <br />
        Total Discount: {{ parseInt(0.05 * p.price) }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    product: {
      type: Array,
      required: true,
    },
  },
};
</script>
