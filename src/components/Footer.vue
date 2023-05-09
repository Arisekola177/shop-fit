<template>
  <div class="flex justify-between items-center">
    <div class="">
      <router-link to="/">
        <h1 class="text-slate-600">
          Shop<span class="text-red-400">Fit</span>
        </h1>
      </router-link>
    </div>

    <div class="text-4xl font-bold">
      <router-link to="/facebook.com">
        <img
          class="w-10 text-teal-500"
          src="../assets/product-images/icon-facebook.svg"
          alt=""
        />
      </router-link>
      <router-link to="/twitter.com">
        <img
          class="w-10 text-teal-500"
          src="../assets/product-images/icon-twitter.svg"
          alt=""
        />
      </router-link>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style></style>
