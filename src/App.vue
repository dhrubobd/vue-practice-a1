<script setup>
import { ref } from 'vue';
import { person } from './data/data';
//For Weather Showing App
const weather = ref(1);

// For Birth Year Guessing App
const birthYear = ref(0);
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

  <hr class="my-10">


  <!-- 
    Weather Showing App (v-show practice)
  -->
  <section class="p-5 text-center">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
        <div class="flex mt-4 md:mt-6 p-5">
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="weather=1">Sunny</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="weather=2">Cloudy</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="weather=3">Rainy</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="weather=4">Stormy</button>
        </div>
        <div class="p-5">
          <div v-show="weather==1">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Weather is Sunny</h5>
            <img src="./assets/images/sunny.png"  />
          </div>
          <div  v-show="weather==2">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Weather is Cloudy</h5>
            <img src="./assets/images/cloudy.png"  />
          </div>
          <div v-show="weather==3">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Weather is Rainy</h5>
            <img src="./assets/images/rainy.png"  />
          </div>  
          <div v-show="weather==4">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Weather is Stormy</h5>
            <img src="./assets/images/stormy.png"  />
          </div>
        </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Birthyear Guessing App (For If Else Practice)
  -->
  <section class="p-5 text-center mx-auto">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Guess My Birth Year</h5>
        <input class="border-2 border-indigo-600" placeholder="Guess Year" type="text" v-model="birthYear">
        <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white text-red-600" v-if="birthYear>0 && birthYear<1983">Your Guessed Me as a Younger Person</h5>
        <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white text-green-500" v-else-if="birthYear==1983">Yes! Correct!</h5>
        <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white text-red-600" v-else-if="birthYear>1983">You Guessed Me as an Older Person</h5>
        <h5 class="mb-2 text-xl font-bold tracking-tight text-gray-900 dark:text-white" v-else>Keep Guessing...</h5>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>
