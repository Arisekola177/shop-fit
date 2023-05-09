<template>
  <div class="">
    <h1 class="text-center text-3xl font-bold underline text-gray-600">
      Shopping Cart
    </h1>
    <div
      class="w-8/12 mx-auto text-center flex justify-between items-center"
      v-for="(product, index) in cartItems"
      :key="product.id"
    >
      <img :src="product.imageUrl" />
      <div>
        <h3 class="text-xl text-slate-800 mb-5 font-bold">
          {{ product.name }}
        </h3>
        <h3 class="text-xl mb-5 font-bold text-slate-800">
          #{{ product.price }}
        </h3>
      </div>

      <button
        @click="remove(index)"
        class="bg-black text-white py-3 px-6 rounded-md"
      >
        Remove From Cart
      </button>
    </div>

    <div class="text-center mt-5">
      <h3 class="text-xl font-bold mb-5">Total: #{{ totalPrice }}</h3>
      <button class="bg-black text-white py-3 px-6 rounded-md">
        Proceed to Checkout
      </button>
    </div>
  </div>
</template>

<script>
import { cartItems } from '../fake-data';

export default {
  name: 'Cart',
  components: {},
  data() {
    return {
      cartItems,
    };
  },
  methods: {
    checkout() {},
    remove(index) {
      this.cartItems.splice(index, 1);
    },
  },
  computed: {
    totalPrice() {
      return this.cartItems.reduce(
        (sum, item) => sum + parseFloat(item.price),
        0
      );
    },
  },
};
</script>
