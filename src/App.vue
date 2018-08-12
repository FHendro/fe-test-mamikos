<template>
  <div id="app">
    <Navigation></Navigation>
    <Forecast></Forecast>
    <LiveCam></LiveCam>
    <News></News>

  </div>
</template>

<script>

import Navigation from './components/Navigation.vue';
import Forecast from './components/Forecast.vue';
import LiveCam from './components/LiveCam.vue';
import News from './components/News.vue';


export default {

  name : 'App',
  components : {
    Navigation,
    Forecast,
    LiveCam,
    News
  }
}
</script>

<style scoped>


</style>
