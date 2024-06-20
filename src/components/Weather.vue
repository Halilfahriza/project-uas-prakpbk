<template>
  <q-page>
    <div class="weather">
      <h1>Weather App</h1>
      <div class="dropdown">
        <button class="dropbtn">Tugas</button>
        <div class="dropdown-content">
          <a v-for="link in dropdownLinks" :key="link.label" :href="link.url" target="_blank">
            {{ link.label }}
          </a>
        </div>
      </div>
      <input v-model="city" placeholder="Enter city" @keyup.enter="getWeather" />
      <button @click="getWeather">Get Weather</button>
      <div v-if="weather">
        <h2>{{ weather.name }}</h2>
        <p>{{ weather.weather[0].description }}</p>
        <p>Temperature: {{ (weather.main.temp - 273.15).toFixed(2) }} °C</p>
        <p>Humidity: {{ weather.main.humidity }} %</p>
        <p>Wind Speed: {{ weather.wind.speed }} m/s</p>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      city: '',
      weather: null,
      dropdownLinks: [
        { label: 'Tugas 1', url: 'https://halilfahriza.netlify.app/' },
        { label: 'Tugas 2', url: 'https://t2-prakpbk-halil.netlify.app/' },
        { label: 'Tugas 3', url: 'https://halill-fahriza.netlify.app/' },
        { label: 'Tugas 4', url: 'https://t4-halil-prakpbk.netlify.app/' },
        { label: 'Tugas 5', url: 'https://t5-t6-223510312-halil.netlify.app/' },
        { label: 'Tugas 6', url: 'https://tugas6-prakpbk-halil.netlify.app/' },
      ],
    };
  },
  methods: {
    async getWeather() {
      const apiKey = 'cc13bd0cae18d876486d73588473a405'; // API key Anda
      const url = `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${apiKey}`;
      try {
        const response = await fetch(url);
        const data = await response.json();
        this.weather = data;
      } catch (error) {
        console.error('Error fetching weather data:', error);
      }
    },
  },
};
</script>

<style scoped>
.weather {
  text-align: center;
  margin-top: 20px;
}
input {
  padding: 10px;
  font-size: 16px;
}
button {
  padding: 10px 20px;
  font-size: 16px;
  margin-left: 10px;
}
.dropdown {
  position: relative;
  display: inline-block;
}
.dropbtn {
  padding: 10px 20px;
  font-size: 16px;
  margin-bottom: 10px;
  cursor: pointer;
}
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #0931b4;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgb(0, 0, 0);
  z-index: 1;
}
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}
.dropdown-content a:hover {
  background-color: #087ae4;
}
.dropdown:hover .dropdown-content {
  display: block;
}
</style>
