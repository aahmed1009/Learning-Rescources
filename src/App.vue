<template>
  <the-header title="Remember ME "></the-header>
  <the-resources> </the-resources>
</template>

<script>


import TheHeader from './components/layouts/TheHeader.vue'
import TheResources from './components/TheResources.vue'
export default {
  components: {
    TheHeader, TheResources
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap');

* {
  box-sizing: border-box;

}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;

}
</style>
