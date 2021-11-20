<template>
  <div class="main" :class="class_name"  v-if="class_name">
    <CityComponent :cityInfo="cityOptions"/>
  </div>
</template>

<script>
// @ is an alias to /src
import CityComponent from '../../components/CityComponent.vue'

export default {
  name: 'City',
  components: {
    CityComponent
  },
  data(){
        return{
           city_name: "",
           cityOptions: {
                name: "",
                tempCelsius: "",
                tempMax: "",
                tempMin: "",
                weather: "",
                icon: "",
                windSpeed: "",
                sunset: "",
                sunrise: "",
                humidity: ""
            },
            class_name: ""
        };
    },
  created(){
      this.city_name = this.$route.params.city_name;
      this.fetchApi(this.city_name);
  },
  methods: {
      async fetchApi(city_name) {
            let url = "https://api.openweathermap.org/data/2.5/weather?q="+city_name+"&units=metric&APPID=44ebf2fe571da3ede316a794a56fe386";
            await fetch(url)
            .then((data) => {
                return data.json()
            }).then((data) => {
                this.cityOptions.name = data.name.toUpperCase();
                this.cityOptions.tempCelsius = data.main.temp.toFixed(0);
                this.cityOptions.tempMax = data.main.temp_max.toFixed(0);
                this.cityOptions.tempMin = data.main.temp_min.toFixed(0);
                this.cityOptions.weather = data.weather[0].main.toLowerCase();
                this.cityOptions.windSpeed = data.wind.speed;
                let sunset = new Date(data.sys.sunset * 1000).toLocaleTimeString('en-US', {hour: 'numeric', minute: 'numeric', hour12: true });
                let sunrise = new Date(data.sys.sunrise * 1000).toLocaleTimeString('en-US', {hour: 'numeric', minute: 'numeric', hour12: true });
                this.cityOptions.sunset = sunset;
                this.cityOptions.sunrise = sunrise;
                this.cityOptions.humidity = data.weather[0].main.toLowerCase();
                this.class_name = data.weather[0].main.toLowerCase();
                this.cityOptions.icon = "http://openweathermap.org/img/wn/"+data.weather[0].icon.toLowerCase()+"@2x.png";
            })
        }
  },
  watch:{
    class_name: {
        handler(){},
        deep: true
    },
    cityOptions: {
        handler(){},
        deep: true
    }
  }
}
</script>

<style scoped lang="scss" src="./style.scss" />