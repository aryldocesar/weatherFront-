<template>
  <div class="container main-home">
    <div class="row justify-content-evenly">
        <div class="col-md-12">
          <h1>WEATHER</h1>
          <h4>select a city</h4>
          <img src="../assets/images/earth.png" alt="earth icon" class="earth-icon">
        </div>
        <div class="col-md-3 col-sm-4 city_name">
          <a href="/city/dallol"><h4>Dallol</h4></a>
        </div>
        <div class="col-md-3 col-sm-4 city_name">
           <a href="/city/fairbanks"><h4>Fairbanks</h4></a>
        </div>
        <div class="col-md-3 col-sm-4 city_name">
          <a href="/city/londres"><h4>Londres</h4></a>
        </div>
        <div class="w-100"></div>
        <div class="col-md-3 col-sm-4 city_name">
          <a href="/city/recife"><h4>Recife</h4></a>
        </div>
        <div class="col-md-3 col-sm-4 city_name">
          <a href="/city/vancouver"><h4>Vancouver</h4></a>
        </div>
        <div class="col-md-3 col-sm-4 city_name">
            <a href="/city/yakutsk"><h4>Yakutsk</h4></a>
        </div>
    </div>
</div>
</template>

<script>
export default {
  name: 'HomeComponent',
  methods: {
    alertCity(city_id){
      console.log(city_id)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss" src="../views/Home/style.scss" />
