<script>
export default {
  data() {
    return {
      categories: ['All', 'Coding', 'Design'],
      selectedCategories: [],
    };
  },
  created() {
    this.selectedCategories = ['All']; // Set 'All' checkbox as initially selected
  },
  watch: {
    selectedCategories() {
      this.$emit('category-change', this.selectedCategories);
    },
  },
  methods: {
    handleCategoryChange() {
      if (this.selectedCategories.includes('All')) {
        this.selectedCategories = ['All']; // If 'All' checkbox is selected, uncheck other checkboxes
      } else {
        this.selectedCategories = this.selectedCategories.filter(category => category !== 'All'); // Remove 'All' checkbox if other checkboxes are selected
      }
      this.$emit('category-change', this.selectedCategories);
    },
  },
};
</script>

<template>
  <div class="w-2/12 ">
    <div class="flex flex-col w-full space-y-10 overflow-y-auto max-h-screen">
      <div class="flex flex-col space-y-5">
        <span class="font-bold text-2xl text-slate-700">Category</span>
        <div v-for="category in categories" :key="category">
          <div class="cursor-pointer flex items-center space-x-2">
            <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
              <input
                class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md"
                type="checkbox"
                :value="category"
                v-model="selectedCategories"
              />
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
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox" value="beginner"
              autocomplete="off" id="boxbegin" />
          </label>
          <label for="boxbegin"> Beginner Friendly </label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox"
              value="intermediate" autocomplete="off" id="boxinter" />
          </label>
          <label for="boxinter"> Intermediate </label>
        </div>
        <div class="cursor-pointer flex items-center space-x-2">
          <label class="flex border-2 border-slate-700 p-[2px] rounded-md">
            <input class="h-5 w-5 appearance-none checked:bg-blue-700 checked:rounded-md" type="checkbox"
              value="alllevels" autocomplete="off" id="boxallev" />
          </label>
          <label for="boxallev"> All levels </label>
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
