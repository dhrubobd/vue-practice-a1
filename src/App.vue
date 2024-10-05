<script setup>
const person =[
  {
    image:'./src/assets/images/person1.png',
    name:'Victoria Harris',
    designation:'CEO',
    bio:'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos quo, tenetur nesciunt repudiandae dicta esse ex nobis facere eveniet minima, veritatis iure aspernatur officiis saepe nulla aperiam autem corrupti assumenda.',
  },
  {
    image:'./src/assets/images/person2.png',
    name:'Mark Kobe',
    designation:'Accountant',
    bio:'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos quo, tenetur nesciunt repudiandae dicta esse ex nobis facere eveniet minima, veritatis iure aspernatur officiis saepe nulla aperiam autem corrupti assumenda.',
  },
  {
    image:'./src/assets/images/person3.png',
    name:'Tannisa Chan',
    designation:'Office Executive',
    bio:'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eos quo, tenetur nesciunt repudiandae dicta esse ex nobis facere eveniet minima, veritatis iure aspernatur officiis saepe nulla aperiam autem corrupti assumenda.',
  }
];
</script>

<template>

  <section class="grid grid-cols-3 gap-3">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <img class="rounded-t-lg" :src="person[0].image" :alt="person[0].name" :title="person[0].name"/>
        </a>
        <div class="p-5 text-left">
            <a href="#">
                <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ person[0].name }}</h5>
            </a>
            <p class="mb-3 font-medium text-xl text-gray-700 dark:text-gray-400">{{ person[0].designation }}</p>
            <p class="mb-3 font-normal">{{ person[0].bio }}</p>
            <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                Know More
                <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                </svg>
            </a>
        </div>
    </div>
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <img class="rounded-t-lg" :src="person[1].image" :alt="person[1].name" :title="person[1].name"/>
        </a>
        <div class="p-5 text-left">
            <a href="#">
                <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ person[1].name }}</h5>
            </a>
            <p class="mb-3 font-medium text-xl text-gray-700 dark:text-gray-400">{{ person[1].designation }}</p>
            <p class="mb-3 font-normal">{{ person[1].bio }}</p>
            <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                Know More
                <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                </svg>
            </a>
        </div>
    </div>
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <img class="rounded-t-lg" :src="person[2].image" :alt="person[2].name" :title="person[2].name"/>
        </a>
        <div class="p-5 text-left">
            <a href="#">
                <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ person[2].name }}</h5>
            </a>
            <p class="mb-3 font-medium text-xl text-gray-700 dark:text-gray-400">{{ person[2].designation }}</p>
            <p class="mb-3 font-normal">{{ person[2].bio }}</p>
            <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                Know More
                <svg class="rtl:rotate-180 w-3.5 h-3.5 ms-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                </svg>
            </a>
        </div>
    </div>
  </section>

</template>

<style scoped>

</style>
