<template>
  <div class="weather-widget">
    <h2>Weather Widget</h2>
    <div class="search-bar">
      <input v-model="city" placeholder="Enter city name" @keyup.enter="getWeather" />
      <button @click="getWeather">Search</button>
    </div>
    <div v-if="weather" class="weather-info">
      <div class="weather-item">
        <p><strong>Location:</strong> {{ weather.name }}</p>
        <div class="weather-border"></div>
      </div>
      <div class="weather-item">
        <p><strong>Temperature:</strong> {{ weather.main.temp }}°C</p>
        <div class="weather-border"></div>
      </div>
      <div class="weather-item">
        <p><strong>Weather:</strong> {{ weather.weather[0].description }}</p>
        <div class="weather-border"></div>
      </div>
    </div>
    <div v-else>
      <p>Enter a city name to see the weather.</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import axios from 'axios'

const city = ref('')
const weather = ref(null)

const getWeather = async () => {
  const apiKey = '23f0987b01236b80c30ceeb06f7c8c22'
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city.value}&units=metric&appid=${apiKey}`

  try {
    const response = await axios.get(url)
    weather.value = response.data
  } catch (error) {
    console.error(error)
    weather.value = null
  }
}
</script>

<style scoped>
.weather-widget {
  padding: 20px;
  border: 1px solid #5a3d6f;
  border-radius: 10px;
  max-width: 750px;
  margin: 50px auto;
  text-align: center;
  background-color: #f8dfe3;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.weather-widget h2 {
  color: #381a1a;
  font-size: 36px;
  font-weight: bold;
  margin-bottom: 20px;
}

.search-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.search-bar input {
  padding: 10px;
  width: 70%;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f5d0d0;
}

.search-bar button {
  padding: 10px;
  border: 1px solid #381a1a;
  background-color: #6d3939;
  color: whitesmoke;
  cursor: pointer;
  border-radius: 5px;
}

.search-bar button:hover {
  background-color: #4e2626;
}

.weather-info {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.weather-item {
  margin: 10px 0;
  border: 1px solid brown;
  border-radius: 5px;
  padding: 10px;
  width: 75%;
  background-color: #f5d0d0;
}

.weather-item p {
  margin: 0 au;
  color: #381a1a;
}

</style>
