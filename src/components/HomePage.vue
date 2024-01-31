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
        <div class="grid grid-cols-3 gap-9 mt-20">
          <div
            class="relative"
            v-for="categorySchema in categoryCardSchema"
            :key="categorySchema.propertyTitle"
          >
            <div class="bg-white top-3 left-4 px-4 py-2 rounded-lg text-red-500 absolute">
              {{ categorySchema.propertyInventory[0] }}
            </div>
            <img
              :src="categorySchema.propertyPic"
              class="rounded-2xl w-96 h-64"
              :alt="categorySchema.propertyTitle"
              width="170px"
              height="170px"
            />
            <div class="px-4 capitalize">
              <h3 class="text-2xl mt-4">{{ categorySchema.propertyTitle }}</h3>
              <h3 class="text-red-500 my-2">{{ categorySchema.propertyType }}</h3>
              <h3 class="text-gray-400">{{ categorySchema.propertyLocation }}</h3>
            </div>
          </div>
        </div>
        <h3 :class="mainBtn" class="mt-12">Explore all Offers</h3>
      </div>
    </div>
    <!-- reviews -->
    <div class="px-52 py-24" :class="colorRed">
      <div class="text-white flex justify-between">
        <div class="w-2/4">
          <h2 class="text-5xl text-black font-black">
            12+ years of helping you find the right Properties
          </h2>
          <article class="mt-12">
            <p>
              Our Mission is to be the most effective real estate platform by offering a transparent
              model that allows homeowners to sell their house and stay in it as a renters
            </p>
            <p class="mt-6">
              As passionate entrepreneurs, but most importantly as family members and responsible
              citizens, we believe that the cornerstone of any business must rely on benefiting
              society while offering a transparent solution.
            </p>
          </article>
        </div>

        <div class="rounded-lg h-96 relative">
          <div
            class="h-[400px] -translate-x-5 absolute top-o left-0 bottom-0 right-0 border-2 border-white border-dotted translate-y-3 rounded-full"
          ></div>
          <img
            src="https://media.istockphoto.com/id/1278101126/photo/handsome-real-estate-agent-is-giving-key-to-the-new-apartment-to-happy-young-couple.jpg?s=612x612&w=0&k=20&c=TXMbxqjrR1NEKXpvQMzIcW0mvRdFWi4pCwaLZo6bo1I="
            alt="unsplash_real_estate"
            class="rounded-full object-cover w-96 h-96"
          />
          <div
            class="h-[400px] translate-x-5 absolute top-o left-0 bottom-0 right-0 border-2 border-white border-dotted translate-y-3 rounded-full"
          ></div>
          <div class="absolute rounded-full z-30 bottom-6 h-16 w-16 bg-white"></div>
          <div
            class="absolute rounded-full z-30 translate-x-36 -translate-y-7 h-14 w-14 bg-white"
          ></div>
          <div
            class="absolute rounded-full z-30 translate-x-80 -translate-y-12 h-8 w-8 bg-white"
          ></div>
        </div>
      </div>
    </div>
    <!-- faq -->
    <div class="px-52 py-24">
      <div class="flex flex-col items-center mx-auto">
        <h3 class="text-2xl font-bold mb-7">frequently asked questions</h3>
        <div v-for="faq in faqs" :key="faq.q" class="mt-5 bg-gray-200 w-4/5 max-w-[900px]">
          <div class="flex bg-white py-4 justify-between items-center border-b border-red-500">
            <h3 class="text-xl font-medium">{{ faq.q }}</h3>
            <AkPlus class="text-3xl" />
          </div>
          <h4 class="px-4 py-2">{{ faq.a }}</h4>
        </div>
      </div>
    </div>
    <!-- reviews -->
    <div class="bg-black px-52 py-24 text-white">
      <div>
        <h3 class="text-2xl flex items-center justify-center">Others service you might need</h3>
        <div class="grid grid-cols-3 gap-8 mt-12">
          <div
            class="pb-4 h-48 rounded-md"
            :class="colorRed"
            v-for="service in services"
            :key="service.title"
          >
            <h3 class="bg-white flex items-center justify-between text-xl px-4 py-4 text-black">
              {{ service.title }} <CaChartNetwork class="font-bold" />
            </h3>
            <p class="p-4">{{ service.content }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { AkPlus } from '@kalimahapps/vue-icons'
// import { AnOutlinedClose } from "@kalimahapps/vue-icons";
import { CaChartNetwork } from '@kalimahapps/vue-icons'
export default {
  name: 'HomePage',
  components: { AkPlus, CaChartNetwork },
  data() {
    return {
      mainBtn: 'mainBtn',
      categoryBtn: 'categoryBtn',
      colorRed: 'colorRed',
      searchHandler: '',
      categoryCardSchema: [
        {
          propertyPic:
            'https://plus.unsplash.com/premium_photo-1675324517011-24d2c741c22f?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8cmVhbCUyMGVzdGF0ZXxlbnwwfHwwfHx8MA%3D%3D',
          propertyTitle: 'alaba house',
          propertyType: '2 Bedroom flat',
          propertyLocation: 'ikorodu',
          propertyInventory: ['for rent', 'rented', 'occupied']
        },
        {
          propertyPic:
            'https://images.unsplash.com/photo-1582407947304-fd86f028f716?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8cmVhbCUyMGVzdGF0ZXxlbnwwfHwwfHx8MA%3D%3D',
          propertyTitle: 'alaba house',
          propertyType: '2 Bedroom flat',
          propertyLocation: 'ikorodu',
          propertyInventory: ['for rent', 'rented', 'occupied']
        },
        {
          propertyPic:
            'https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8cmVhbCUyMGVzdGF0ZXxlbnwwfHwwfHx8MA%3D%3D',
          propertyTitle: 'alaba house',
          propertyType: '2 Bedroom flat',
          propertyLocation: 'Imota',
          propertyInventory: ['for rent', 'rented', 'occupied']
        },
        {
          propertyPic:
            'https://images.unsplash.com/photo-1580587771525-78b9dba3b914?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fHJlYWwlMjBlc3RhdGV8ZW58MHx8MHx8fDA%3D',
          propertyTitle: 'alaba house',
          propertyType: '2 Bedroom flat',
          propertyLocation: 'Odogunyan',
          propertyInventory: ['for rent', 'rented', 'occupied']
        },
        {
          propertyPic:
            'https://images.unsplash.com/photo-1479839672679-a46483c0e7c8?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTl8fHJlYWwlMjBlc3RhdGV8ZW58MHx8MHx8fDA%3D',
          propertyTitle: 'Ogijo house',
          propertyType: 'A Roomself contain',
          propertyLocation: 'Ogijo',
          propertyInventory: ['for rent', 'rented', 'occupied']
        },
        {
          propertyPic:
            'https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTR8fHJlYWwlMjBlc3RhdGV8ZW58MHx8MHx8fDA%3D',
          propertyTitle: 'alaba house',
          propertyType: '2 Bedroom flat',
          propertyLocation: 'ikorodu',
          propertyInventory: ['for rent', 'rented', 'occupied']
        }
      ],
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
      ],
      faqs: [
        {
          q: 'What are the common closing costs associated with purchasing property',
          a: 'Loan Origination Fee: This fee covers the administrative costs of processing the loan and is usually around 1% of the loan amount'
        },
        {
          q: 'What is the eviction process if I fail to pay rent or violate the lease agreement?',
          a: 'The eviction process varies by jurisdiction, but it usually involves the landlord providing notice to the tenant, giving them an opportunity to rectify the issue or vacate the property. If the tenant does not comply, the landlord may proceed with the eviction process through the court system.s'
        },
        {
          q: 'What is a lease agreement',
          a: 'A lease agreement is a written contract between the landlord and tenant that outlines the terms and conditions of the rental. It includes details such as the rental period, monthly rent, security deposit, maintenance responsibilities, and any rules or restrictions.'
        },
        {
          q: "What is renter's insurance, and do I need it?",
          a: "Renter's insurance is an insurance policy that provides coverage for a tenant's belongings and liability. While it is not legally required, it is highly recommended as it can protect your personal property in the event of theft, accidents, or natural disasters."
        }
      ],
      services: [
        {
          title: 'Agricultural business',
          content:
            'We try as much as possible to discourage lazy asset ownership and as such provide our subscribers with properties that have the uniqueness of RENTAL INCOME'
        },
        {
          title: 'Contract',
          content:
            'We try as much as possible to discourage lazy asset ownership and as such provide our subscribers with properties that have the uniqueness of RENTAL INCOME'
        },
        {
          title: 'Networking',
          content:
            'We also network by creating and helping different individual skill & unskill labour for your job opportunities througout the nation.  providing you with the best'
        },
        {
          title: 'E-commerce',
          content:
            'We cover up througout the nation without wasting time. True our expert disperse and connection with other logistics company.'
        },
        {
          title: 'Crypto',
          content:
            'We cover up througout the nation without wasting time. True our expert disperse and connection with other logistics company.'
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

<style scoped>
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

.colorRed {
  background-color: red;
}

.mainBtn:hover {
  background-color: rgb(214, 0, 0);
}
</style>
