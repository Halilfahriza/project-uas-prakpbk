<template>
  <q-layout view="hHh lpR fFf">

    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQeC1OJG1x9ZCDY8xKG-S5OLdPoZ-t1xfCxMg&s">
          </q-avatar>
          TodayWeather
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <Weather />
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            
          </q-avatar>
          <div></div>
        </q-toolbar-title>
        <div class="q-mr-md">© 2024 Halil Fahriza</div>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import Weather from './components/Weather.vue';

export default {
  name: 'App',
  components: {
    Weather,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000408;
  margin-top: 60px;
  background: url('https://path.to/your/background-image.jpg') no-repeat center center fixed;
  background-size: cover;
}

.q-footer .q-toolbar-title {
  flex: 1;
}

/* Optional: Adding a semi-transparent background to the header and footer */
.q-header, .q-footer {
  background-color: rgba(1, 10, 3, 0.7);
}

/* Optional: Adding padding to the page container for better spacing */
.q-page-container {
  padding: 20px;
  background: rgba(154, 0, 226, 0.8); /* Semi-transparent white background */
  border-radius: 8px;
}
</style>
