<template>
  <div>
    <h1
      class="text-center text-xl font-semibold uppercase md:mb-10 md:text-2xl"
    >
      {{ title }}
    </h1>
    <div class="w-full">
      <div
        class="w-full m-auto p-6 flex flex-wrap justify-between items-center md:w-10/12 md:items-start"
      >
        <div
          class="w-60 border-4 mt-8 p-4 mx-auto text-center rounded-lg shadow-lg lg:w-80"
          v-for="product in products"
          :key="product.id"
        >
          <img class="w-full" :src="product.imageUrl" />
          <h2 class="text-2xl text-gray-700 font-bold">{{ product.name }}</h2>
          <p class="text-xl font-bold mt-3">#{{ product.price }}</p>
          <div class="flex flex-col">
            <router-link v-bind:to="'/products/' + product.id">
              <button
                class="bg-slate-500 py-3 px-6 text-white rounded-md font-semibold mt-2 w-full"
              >
                View Details
              </button>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { products } from '../fake-data';

export default {
  name: 'Products',
  data() {
    return {
      title: 'Our Products',
      products,
    };
  },
};
</script>
