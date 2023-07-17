<script>
import navbar from './components/navbar.vue';
import katalog from './components/katalog.vue';
import list from './components/list.vue';

export default {
  components: {
    navbar,
    katalog,
    list,
  },
  data() {
    return {
      products: [
        { id: 0, name: 'Vanilla JavaScript Pada Website Development', harga: 'Rp 0', category: 'Coding' , image:'https://buildwithangga.com/storage/assets/thumbnails/freelancer_basic_thumb.png' },
        { id: 1, name: 'Flutter Mobile Apps', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20flutter%20mobile%20apps%20online%20gratis%20buildwith%20angga.png' },
        { id: 2, name: 'CSS Website Design', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/kelas%20css%20website%20design%20gratis%20buildwith%20angga.png' },
        { id: 3, name: 'PHP Laravel Web Development', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail_larafree.png' },
        { id: 4, name: 'React JavaScript', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20react%20javascript%20web%20development%20buildwith%20angga.png' },
        { id: 5, name: 'Vue JavaScript Framework', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail_vue_starter.png' },
        { id: 6, name: 'PHP Dasar Website Development', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20es6%20buildwith%20angga.png' },
        { id: 7, name: 'CSS Tailwind Web Design', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20css%20tailwind%20web%20design%20buildwith%20angga.png' },
        { id: 8, name: 'ES6 Dasar', harga: 'Rp 0', category: 'Coding', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20es6%20buildwith%20angga.png' },
        { id: 9, name: 'Learn Figma For Beginner', harga: 'Rp 0', category: 'Design', image:'https://buildwithangga.com/storage/assets/thumbnails/gkm59j5l-63.png' },
        { id: 10, name: 'UI Design: Wireframe to Visual Design', harga: 'Rp 0', category: 'Design', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%20ui%20design%20wireframe%20ke%20visual%20design%20buildwith%20angga.png' },
        { id: 11, name: 'Blender: Design 3D Illustration', harga: 'Rp 0', category: 'Design', image:'https://buildwithangga.com/storage/assets/thumbnails/thumbnail%20kelas%203d%20design%20blender%20buildwith%20angga.png' },
        { id: 12, name: 'Adobe Illustration: How to create Icon for UI', harga: 'Rp 0', category: 'Design', image:'https://buildwithangga.com/storage/assets/thumbnails/Thumbnail%20kelas%20Icon%20user-interface%20design%20buildwith%20angga.png' },
      ],
      filteredProducts: [],
      level: lemao,
    };
  },
  methods: {
    handleCategoryChange(selectedCategories) {
      if (selectedCategories.includes('All')) {
        this.filteredProducts = this.products;
      } else {
        this.filteredProducts = this.products.filter((product) =>
          selectedCategories.includes(product.category)
        );
      }
    },
  },
};
</script>


<template>
  <div class="bg-slate-100">
  <navbar />
  <div class="pt-10 w-10/12 border-4 mx-auto">
    <div class="flex flex-col text-2xl font-bold text-slate-800">
      <span>Browse Kelas</span>
      <span>Sesuai Karir Kamu</span>
    </div>
    <div class="flex flex-row pt-10">
      <katalog @category-change="handleCategoryChange" />
      <list :filteredProducts="filteredProducts" />
    </div>
  </div>
</div>
</template>