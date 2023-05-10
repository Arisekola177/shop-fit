<template>
  <div class="w-full p-8 mt-5 mb-5">
    <div class="w-10/12 mx-auto">
      <div class="flex justify-between items-center">
        <div class="text-xl font-bold uppercase">
          <router-link class="flex justify-between items-center" to="/">
            <img src="../assets/product-images/icons8-trainers-50.png" />
            <h1 class="text-slate-600">
              Shop<span class="text-red-400">Fit</span>
            </h1>
          </router-link>
        </div>

        <div>
          <router-link to="/cart">
            <img class="w-10" src="../assets/product-images/icon-cart.svg" />
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<style></style>
