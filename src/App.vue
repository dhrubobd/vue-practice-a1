<script setup>
import { reactive, ref } from 'vue';
import { person } from './data/data';
//For Weather Showing App
const weather = ref(1);

// For Birth Year Guessing App
const birthYear = ref(0);

// Class Binding
const textRed = 'text-red-600';

const messageType = ref(0);
const  inputWhite = 'bg-white-600';
const  inputGreen = 'bg-green-600';
const  inputRed = 'bg-red-600';

// Class Binding With Birth Year Guessing

const bYear = ref(0);
const  normalHighlight = 'bg-white-600 text-black-600';
const successHighlight = 'bg-green-600 text-white';
const errorHighlight = 'bg-red-600 text-white';


// Looping / List Rendering
const items = [1,2,3,4,5,6];

//Looping / List Rendering with index
const toys = [
  "Play Doe", "Puppets", "Toy Train", "Castel Making Toy", "Toy Cars", "Musical Toys"
];

// Tasks filtering App
const tasks = [
  {id:1, title:"Make ERD Diagram", tstatus:"completed" },
  {id:2, title:"Website Design", tstatus:"ongoing" },
  {id:3, title:"Making Components", tstatus:"ongoing" },
  {id:4, title:"Meeting With Clients", tstatus:"completed" },
  {id:5, title:"Technical Documentation", tstatus:"pending" },
  {id:6, title:"Project Proposal Making", tstatus:"pending" },
  {id:7, title:"Social Media Management", tstatus:"ongoing" },
  {id:7, title:"Database Desing", tstatus:"completed" },
];

const pendingBG = 'bg-red-600 text-white';
const ongoingBG = 'bg-orange-600 text-white';
const completedBG = 'bg-green-600 text-white';

const taskFilter = ref('all');

function getTasks(taskFilter){
  if(taskFilter=='all'){
    return tasks;
  }
  return tasks.filter(task=>taskFilter==task.tstatus);
}

// City Weather

const weatherData = [
  {
    city: 'Dhaka',
    weather: 'cloudy',
    temperature: '12'
  },
  {
    city: 'Chittagong',
    weather: 'sunny',
    temperature: '18'
  },
  {
    city: 'Comilla',
    weather: 'rainy',
    temperature: '16'
  },
  {
    city: 'Barishal',
    weather: 'sunny',
    temperature: '19'
  },
  {
    city: 'Sylhet',
    weather: 'rainy',
    temperature: '16'
  },
  {
    city: 'Rajshahi',
    weather: 'stormy',
    temperature: '15'
  }
];

const theWeatherData = reactive({
    city: weatherData[0].city,
    weather: weatherData[0].weather,
    temperature: weatherData[0].temperature
  });
  const theIndex = 0;
function changeWeatherReport(city,weather,temperature){
  
  theWeatherData.city = city;
  theWeatherData.weather = weather;
  theWeatherData.temperature = temperature;
  
}

// Accordion

const accordionData = reactive([
  {
    question: 'What is Material Tailwind?',
    answer: 'Material Tailwind is a framework that enhances Tailwind CSS with additional styles and components.',

  },
  {
    question: 'How to use Material Tailwind?',
    answer: 'You can use Material Tailwind by importing its components into your Tailwind CSS project.',

  },

]);
const selectedIndex = ref(0);

// Quiz
const countries =reactive([
  {name: 'Bangladesh',capital:'Dhaka'},
  {name: 'Canada',capital:'Ottowa'},
  {name: 'Japan',capital:'Tokyo'},
  {name: 'France',capital:'Paris'},
]);

const capitals = ["Ottowa","Dhaka","Paris", "Tokyo"];

let submitted = ref(0);
function getScore(){
  let score = 0;
  countries.forEach(country=>{
    if(country.answer === country.capital){
      score++;
    }
  });
  return score;
}


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
  <section class="p-5 text-center flex items-center flex-col">
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
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Guess My Birth Year</h5>

        <input class="border-2 border-indigo-600 text-center" placeholder="Guess Year" type="text" v-model="birthYear">

        <h5 class="mb-2 text-xl tracking-tight text-red-600" v-if="birthYear>0 && birthYear<1983">You Guessed Me as an Older Person</h5>
        <h5 class="mb-2 text-xl tracking-tight text-green-500" v-else-if="birthYear==1983">Yes! Correct!</h5>
        <h5 class="mb-2 text-xl tracking-tight text-red-600" v-else-if="birthYear>1983">Your Guessed Me as a Younger Person</h5>
        <h5 class="mb-2 text-xl tracking-tight text-gray-900" v-else>Keep Guessing...</h5>
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Class Binding
  -->
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight" :class="textRed">Class Binding Example</h5>
        <input class="border-2 border-indigo-600 text-center" placeholder="Click on The Buttons Bellow" type="text" :class="messageType=='success'?inputGreen:messageType=='error'?inputRed:inputWhite">
        <div class="flex mt-4 md:mt-6 p-5">
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="messageType='success'">Success</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="messageType='error'">Error</button>
        </div>
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Class Binding With Birth Year Guessing
  -->
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Guess My Birth Year</h5>

        <input class="border-2 border-indigo-600 text-center" placeholder="Guess Year" type="text" v-model="bYear" :class="bYear>0 && bYear<1983 ? errorHighlight
        :bYear==1983 ? successHighlight : bYear>1983 ? errorHighlight : normalHighlight">
        <h5 class="mb-2 text-xl tracking-tight text-gray-900" >Keep Guessing... You will get a Green Signal If You Findout my Birth Year</h5>
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Looping / List Rendering
  -->
  <section class="grid grid-cols-3 gap-3">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700" v-for="item in items">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Box Number {{ item }}</h5>
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Looping / List Rendering with index
  -->
  <section class="grid grid-cols-3 gap-3">
    <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700" v-for="(toy,index) in toys">
      <div class="p-5">
        <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Box Number {{ index+1 }} has {{ toy }}</h5>
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    Tasks Filtering App
  -->
  <section class="flex items-center flex-col">
    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Filter Tasks</h5>
    <div class="flex mt-4 md:mt-6 p-5">
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="taskFilter='all'">All</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="taskFilter='pending'">Pending</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="taskFilter='ongoing'">Ongoing</button>
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="taskFilter='completed'">Completed</button>
    </div>
    <div class="grid grid-cols-3 gap-3">
      <div class="border border-gray-500 shadow p-5 my-2 ms-2 text-left text-lg" v-for="(task, index) in getTasks(taskFilter)" :key="index+1" :class="task.tstatus=='pending'? pendingBG : task.tstatus=='ongoing'? ongoingBG:completedBG">
        {{ index+1 }}. {{ task.title }}
      </div>
    </div>
  </section>
  <hr class="my-10">
  <!-- 
    City Weather
  -->
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-[600px] bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">City Weather</h5>
        <div class="flex mt-4 md:mt-6 p-5">
            <button class="py-2 px-4 ms-2 text-sm font-medium text-gray-900 focus:outline-none bg-white rounded-lg border border-gray-200 hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-4 focus:ring-gray-100 dark:focus:ring-gray-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700" type="button" @click="changeWeatherReport(cityWeather.city, cityWeather.weather, cityWeather.temperature)" v-for="(cityWeather,index) in weatherData" :key="index+1">{{cityWeather.city}}</button>
        </div>
        <div class="p-5">
          <div v-show="theWeatherData.weather == 'sunny'">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{theWeatherData.city}}: Sunny</h5>
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Temperature: {{theWeatherData.temperature}}°C</h5>
            <img src="./assets/images/sunny.png"  />
          </div>
          <div  v-show="theWeatherData.weather == 'cloudy'">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{theWeatherData.city}}: Cloudy</h5>
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Temperature: {{theWeatherData.temperature}}°C</h5>
            <img src="./assets/images/cloudy.png"  />
          </div>
          <div v-show="theWeatherData.weather == 'rainy'">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{theWeatherData.city}}: Rainy</h5>
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Temperature: {{theWeatherData.temperature}}°C</h5>
            <img src="./assets/images/rainy.png"  />
          </div>  
          <div v-show="theWeatherData.weather == 'stormy'">
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{theWeatherData.city}}: Stormy</h5>
            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Temperature: {{theWeatherData.temperature}}°C</h5>
            <img src="./assets/images/stormy.png"  />
          </div>
        </div>
    </div>
  </section>
  <hr class="my-10">

  <!-- 
    Accordion
  -->
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-[600px] bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Accordion</h5>
      <div class="border-b border-slate-200" v-for="(accordion,index) in accordionData" :key="index">
        <button  class="w-full flex justify-between items-center py-5 text-slate-800" @click="selectedIndex=index">
          <span>{{ accordion.question }}</span>
          <span  class="text-slate-800 transition-transform duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="w-4 h-4">
              <path d="M8.75 3.75a.75.75 0 0 0-1.5 0v3.5h-3.5a.75.75 0 0 0 0 1.5h3.5v3.5a.75.75 0 0 0 1.5 0v-3.5h3.5a.75.75 0 0 0 0-1.5h-3.5v-3.5Z" />
            </svg>
          </span>
        </button>
        <div class="transition-all duration-300 ease-in-out" v-show="index==selectedIndex">
          <div class="p-5 text-sm text-slate-500 text-left">
            {{ accordion.answer }}
          </div>
        </div>
      </div>
    </div>
  </section>
  <!--
    Quiz
  -->
  <section class="p-5 text-center flex items-center flex-col">
    <div class="max-w-[600px] bg-white border border-gray-200 rounded-lg shadow p-5">
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Quiz</h5>
      <!--
      <div>{{ countries }}</div>
      -->
      <div class="border card text-xl text-white bg-black" v-show="submitted == 1">
          Your Score: <span class="text-red-600">{{ getScore() }}</span> 
      </div>
      <template v-for="country in countries" :key="country.name">
        <div class="text-left text-xl font-bold">What is the Capital of {{country.name}}?</div>
        <template v-for="capital in capitals" :key="capital">
          <input :name="country.name" type="radio" v-model="country.answer" :value="capital"  class="m-5 text-left"> <label for="" class="ml-2 mr-2">{{ capital }}</label> 
        </template>
      </template>
      <div>
        <button @click="submitted=1" type="button" class="border p-5 cursor-pointer">Submit</button>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>
