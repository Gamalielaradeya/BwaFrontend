<script>
export default {
  data() {
    return {
      categories: ['All', 'Coding', 'Design'],
      selectedCategories: [],
      levels: ['Beginner Friendly', 'Intermediate', 'All levels'],
      selectedLevels: []
    }
  },
  created() {
    this.selectedCategories = ['All'] // Set 'All' checkbox as initially selected
    console.log('selectedCategories:', this.selectedCategories); // Log the current value
    this.selectedLevels = ['allLevels']
  },
  watch: {
    selectedCategories() {
      this.$emit('category-change', this.selectedCategories);
      console.log('selectedCategories:', this.selectedCategories); // Log the updated value
    },
    selectedLevels(){
      this.$emit('level-change', this.selectedLevels);
      console.log('selectedLevels', this.selectedLevels);
    }
  },
  methods: {
    handleCategoryChange(category) {
      if (category === 'All') {
        this.selectedCategories = ['All'];
      } else {
        if (this.selectedCategories.includes('All')) {
          this.selectedCategories = this.selectedCategories.filter(
            (category) => category !== 'All'
          );
        }
      }
      this.$emit('category-change', this.selectedCategories);
      console.log('selectedCategories:', this.selectedCategories); // Log the updated value
    },
    handleLevelsChange(level) {
      if (level === 'All levels') {
        this.selectedLevels = ['beginner', 'intermediate', 'allLevels'];
      } else {
        this.selectedLevels = level === 'Beginner Friendly' ? ['beginner'] : ['intermediate'];
      }
      this.$emit('level-change', this.selectedLevels);
      console.log('selectedLevels:', this.selectedLevels); // Log the updated value
    },
  }
}
</script>

<template>
  <div class="w-2/12">
    <div class="flex flex-col w-full space-y-10 overflow-y-auto max-h-screen">
      <div class="flex flex-col space-y-5">
        <span class="font-bold text-2xl text-slate-700">Category</span>
        <div v-for="category in categories" :key="category">
          <div class="cursor-pointer flex items-center space-x-2">
            <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
              <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" :value="category" v-model="selectedCategories" @change="handleCategoryChange(category)" />
            </label>
            <label>{{ category }}</label>
          </div>
        </div>
      </div>

      <div class="flex flex-col space-y-5">
        <span class="font-bold text-2xl text-slate-700">Sort</span>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="baru"
              autocomplete="off" id="boxbaru" />
          </label>
          <label for="boxbaru"> Baru Rilis </label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="populer"
              autocomplete="off" id="boxpopuler" />
          </label>
          <label for="boxpopuler"> Terpopuler </label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="promo"
              autocomplete="off" id="boxpromo" />
          </label>
          <label for="boxpromo"> Sedang Promo </label>
        </div>
      </div>

      <div class="flex flex-col space-y-5">
        <span class="font-bold text-2xl text-slate-700">Level</span>
        <div v-for="level in levels" :key="level">
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" :value="level" v-model="selectedLevels" @change="handleLevelsChange(level)"/>
          </label>
          <label>{{ level }} </label>
        </div>
      </div>
      </div>

      <div class="flex flex-col space-y-5">
        <span class="font-bold text-2xl text-slate-700">Type</span>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="starter"
              autocomplete="off" id="boxstarter" />
          </label>
          <label for="boxstarter"> Starter (Rp 0)</label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="freemium"
              autocomplete="off" id="boxfremium" />
          </label>
          <label for="boxfremium"> Freemium (Rp 0) </label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="premium"
              autocomplete="off" id="boxpremium" />
          </label>
          <label for="boxpremium"> Premium </label>
        </div>
      </div>
    </div>
  </div>
</template>
