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
        { id: 0, name: 'Vanilla JavaScript Pada Website Development', harga: 'Rp 0', category: 'Coding' },
        { id: 1, name: 'Flutter Mobile Apps', harga: 'Rp 0', category: 'Coding' },
        { id: 2, name: 'CSS Website Design', harga: 'Rp 0', category: 'Coding' },
        { id: 3, name: 'PHP Laravel Web Development', harga: 'Rp 0', category: 'Coding' },
        { id: 4, name: 'React JavaScript', harga: 'Rp 0', category: 'Coding' },
        { id: 5, name: 'Vue JavaScript Framework', harga: 'Rp 0', category: 'Coding' },
        { id: 6, name: 'PHP Dasar Website Development', harga: 'Rp 0', category: 'Coding' },
        { id: 7, name: 'CSS Tailwind Web Design', harga: 'Rp 0', category: 'Coding' },
        { id: 8, name: 'ES6 Dasar', harga: 'Rp 0', category: 'Coding' },
        { id: 9, name: 'Learn Figma For Beginner', harga: 'Rp 0', category: 'Coding' },
        { id: 10, name: 'UI Design: Wireframe to Visual Design', harga: 'Rp 0', category: 'Design' },
        { id: 11, name: 'Blender: Design 3D Illustration', harga: 'Rp 0', category: 'Design' },
        { id: 12, name: 'Adobe Illustration: How to create Icon for UI', harga: 'Rp 0', category: 'Design' },
      ],
      filteredProducts: [],
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