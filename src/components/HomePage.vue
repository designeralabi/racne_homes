<template>
  <div class="">
    <div class="flex flex-col items-center justify-center bg-black p-52">
      <h1 class="text-white font-bold text-6xl">
        Best <span class="text-red-400 font-black">Real Estate</span> Investment
      </h1>
      <h3 class="text-white mt-9 text-base">
        Landbanking - Buy and Build - Short Let - Long Lease - Multi Unit Apartment
      </h3>
      <div class="bg-white h-16 rounded-lg px-2 py-0 flex items-center mt-10 w-[700px] mx-auto">
        <input
          type="text"
          name="search"
          id="search"
          v-model="searchHandler"
          class="bg-transparent outline-none border-none w-full pl-4"
          placeholder="search for city, neigbhour, agent, address"
        />
        <h3 :class="mainBtn">Search</h3>
      </div>
    </div>
    <!-- category -->
    <div class="px-52 py-24 flex justify-center">
      <div class="mx-auto flex flex-col items-center">
        <h3 class="text-4xl mb-12 font-bold">Choose a category for you</h3>
        <!-- category group -->
        <div class="flex items-center space-x-2 rounded-md bg-white shadow-gray-200 shadow-md p-4">
          <h3 v-for="category in findCategory" :key="category.title" :class="categoryBtn" class="">
            {{ category.title }}
          </h3>
        </div>
        <!-- categoryCard -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mainBtn: 'mainBtn',
      categoryBtn: 'categoryBtn',
      searchHandler: '',
      findCategory: [
        {
          title: 'LandBanking'
        },
        {
          title: 'Residential'
        },
        {
          title: 'Short Let'
        },
        {
          title: 'Long Lease'
        },
        {
          title: 'Multi Unit Apartment'
        }
      ]
    }
  },
  computed: {
    categoryBtnHover() {
      return ''
    }
  }
}
</script>

<style>
.mainBtn {
  background-color: red;
  padding: 10px 40px;
  border-radius: 8px;
  color: whitesmoke;
  cursor: pointer;
  transition: all 1s ease-in-out;
}

.categoryBtn {
  background-color: black;
  padding: 12px 40px;
  border-radius: 8px;
  color: whitesmoke;
  cursor: pointer;
  transition: all 1s ease-in-out;
}

.categoryBtnHover {
  background-color: rgb(214, 0, 0);
}

.mainBtn:hover {
  background-color: rgb(214, 0, 0);
}
</style>
