<template>
    <q-page>
      <div class="layar">
        <iframe src="https://halilfahriza.netlify.app/" frameborder="0" width="100%" height="100%"></iframe>
      </div>
    </q-page>
  </template>
  
  <script>
  export default {
    name: 'EmbeddedPage'
  };
  </script>
  
  <style scoped>
  .layar {
    position: fixed;
    width: 100vw;
    height: 100vh;
    background-color: white;
    overflow: hidden;
  }
  </style>
  