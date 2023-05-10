<template>
  <div class="w-full">
    <div
      class="w-full flex flex-col text-center md:flex-row justify-between items-center gap-10"
    >
      <div class="w-6/12">
        <img class="w-96 mx-auto" :src="product.imageUrl" />

        <h1 class="text-xl md:text-3xl text-teal-400 font-semibold mb-5">
          {{ product.name }}
        </h1>
        <p class="text-xl font-semibold md:text-2xl font-extrabold mb-4">
          #{{ product.price }}
        </p>
        <p class="text-lg md:text-2xl font-semibold">
          Average rating: {{ product.averageRating }}
        </p>
      </div>

      <div class="w-full md:w-6/12">
        <h2 class="text-xl text-center text-slate-700 font-bold mb-5">
          Description
        </h2>
        <p
          class="text-normal text-center p-6 md:text-normal text-start mb-5 p-4"
        >
          {{ product.description }}
        </p>
        <div></div>
        <button
          @click="addToCart"
          class="bg-gray-800 w-80 text-lg font-bold text-white mt-5 rounded-lg py-3 px-6 md:py-6 px-12"
          :class="{ 'bg-gray-600': isInCart }"
        >
          {{ button }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { products } from '../fake-data';
import { cartItems } from '../fake-data';

export default {
  name: 'ProductDetails',
  component: {},
  data() {
    return {
      button: 'Add to Cart',
      product: products.find((p) => p.id === this.$route.params.id),
      cartItems,
      isInCart: false,
    };
  },
  methods: {
    addToCart() {
      this.cartItems.push(this.product);
      this.isInCart = !this.isInCart;
      this.button = 'Added to Cart';
    },
  },
};
</script>
