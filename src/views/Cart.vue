<template>
  <div class="w-full">
    <h1
      class="text-xl text-center md:text-3xl font-bold underline text-gray-600"
    >
      Shopping Cart
    </h1>
    <div
      class="w-10/12 mx-auto mt-5 flex justify-between items-center mt-4 text-center md:w-10/12 mx-auto"
      v-for="(product, index) in cartItems"
      :key="product.id"
    >
      <img class="w-20 md:w-4/12 lg:w-2/12" :src="product.imageUrl" />
      <div class="flex flex-col items-center">
        <h3 class="text-sm text-slate-800 font-bold md:text-xl mb-5">
          {{ product.name }}
        </h3>
        <h3 class="text-sm mb-5 font-bold text-slate-800 md:text-2xl">
          #{{ product.price }}
        </h3>
      </div>
      <div>
        <button
          @click="remove(index)"
          class="hidden md:block bg-black text-sm text-white p-2 rounded-md py-3 px-6"
        >
          Remove From Cart
        </button>
        <img
          @click="remove(index)"
          class="block md:hidden"
          src="../assets/product-images/icons8-trash-24.png"
        />
      </div>
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
