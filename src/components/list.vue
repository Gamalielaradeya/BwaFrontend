<script>
export default {
  props: {
    filteredProducts: {
      type: Array,
      required: true,
    },
  },
};
</script>


<template>
    <div class="flex w-10/12">
      <div class="w-full grid grid-cols-3 px-2 gap-x-4 gap-y-6">
        <transition-group name="fade" mode="out-in">
        <div v-for="product in filteredProducts" :key="product.id">
          <div class="flex flex-col h-full group">
            <a href="" class="flex items-center justify-center relative">
              <img src="https://buildwithangga.com/themes/front/images/play_btn_blue.svg" alt="tombolpley"
                class="absolute translate-y-36 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition ease-in-out duration-700">
              <img :src="product.image" alt="gambar" class="rounded-t-xl">
            </a>
            <div class="px-2 bg-white py-4 rounded-xl z-10">
              <div class="h-14">
                <span class="font-semibold text-xl" id="name">{{ product.name }}</span>
              </div>
              <div class="mt-2">
                <span class="text-slate-700" id="harga">{{ product.harga }}</span>
              </div>
              <div class="flex flex-row items-center justify-between space-x-1 w-full">
                <div class="flex flex-row">
                  <div class="flex flex-row">
                    <img src="https://buildwithangga.com/themes/front/images/ic_star.svg" alt=""
                      class="w-6">
                    <img src="https://buildwithangga.com/themes/front/images/ic_star.svg" alt=""
                      class="w-6">
                    <img src="https://buildwithangga.com/themes/front/images/ic_star.svg" alt=""
                      class="w-6">
                    <img src="https://buildwithangga.com/themes/front/images/ic_star.svg" alt=""
                      class="w-6">
                    <img src="https://buildwithangga.com/themes/front/images/ic_star.svg" alt=""
                      class="w-6">
                  </div>
                  <div>
                    <span>(13,840)</span>
                  </div>
                </div>
                <div>
                  <img src="https://buildwithangga.com/themes/front/images/ic_lv_ez.svg" alt="" class="w-6">
                </div>
              </div>
            </div>
          </div>
        </div>
    </transition-group>
      </div>
    </div>
  </template>
  
  <style scoped>
  .fade-item {
    transition: opacity 0.5s;
  }
  
  .fade-enter-active {
    transition: opacity 0.5s;
  }
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
  </style>
 