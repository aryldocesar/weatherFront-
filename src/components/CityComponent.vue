<template>
  <div class="container main-city">
    <div class="d-flex justify-content-start">
      <a href="/"><img src="../assets/images/arrow-left.png" alt="earth icon" class="earth-icon"></a>
    </div>
    <div class="row justify-content-evenly">
        <div class="col-md-12 col-sm-12">
          <h1>{{cityInfo.name}}</h1>
          <h4>{{cityInfo.weather}}</h4>
        </div>
        <div>
             <span class="temp_big">{{cityInfo.tempCelsius}}<sup class="icon-celsius">&deg;C </sup></span>
        </div>
        <div class="col-md-12 col-sm-12 ">
          <img :src="cityInfo.icon" alt="" class="icon-weather-main">
        </div>
    </div>
    <div class="row justify-content-evenly">
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">dawn</h5> <!-- alter to get from the API [dawn morning afternoon night]-->
          <img src="http://openweathermap.org/img/wn/01n@2x.png" class="icon-weather">
          <br>
          <span class="daily-info">22°</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">morning</h5>
          <img src="http://openweathermap.org/img/wn/02d@2x.png" class="icon-weather">
           <br>
          <span class="daily-info">19°</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">afternoon</h5>
          <img src="http://openweathermap.org/img/wn/01d@2x.png" class="icon-weather">
           <br>
          <span class="daily-info">15°</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">night</h5>
          <img src="http://openweathermap.org/img/wn/10n@2x.png" class="icon-weather">
          <br>
          <span class="daily-info">17°</span>
        </div>
    </div>
    <div class="row justify-content-evenly city-obs">
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">wind speed</h5> <!-- alter to get from the API -->
          <span>{{cityInfo.windSpeed}} m/s</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">sunrise</h5>
          <span>{{cityInfo.sunrise}}</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">sunset</h5>
          <span>{{cityInfo.sunset}}</span>
        </div>
        <div class="col-md-3 col-sm-3">
          <h5 class="info-text">humidity</h5>
          <span>{{cityInfo.humidity}}%</span>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityComponent',
  data(){
          return{};
    },
  props:{
    cityInfo: Object
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss" src="../views/City/style.scss" />
