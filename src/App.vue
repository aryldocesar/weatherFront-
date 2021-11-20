<template>
  <div id="app">
    <router-view/>
  </div>
</template>


<style lang="scss">
@import '@/assets/scss/_main';

html, body {
    height:100%; /*both html and body*/
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}

</style>
