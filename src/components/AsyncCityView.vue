<template>
  <div></div>
</template>

<script setup>
import axios from 'axios';
import { useRoute } from 'vue-router';

const route = useRoute();
const getWeatherData = async () => {
  try {
    const weatherData = await axios.get(
      `https://api.openweathermap.org/data/2.5/weather?lat=${route.query.lat}&lon=${route.query.lng}&appid=700d29913d6cc2f001b2ce0faccf8466&units=imperial`
    );

    return weatherData;
  } catch (err) {
    console.log(err);
  }
};
const weatherDater = await getWeatherData();
console.log(333, weatherDater);
</script>
