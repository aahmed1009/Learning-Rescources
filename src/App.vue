<template>
  <the-header title="Remember ME "></the-header>
  <storedRescources :resources="storedRescources"></storedRescources>
</template>

<script>

import storedRescources from './components/StoredResources.vue'
import TheHeader from './components/layouts/TheHeader.vue'

export default {
  components: {
    storedRescources
    ,
    TheHeader
  },

  data() {
    return {
      storedRescources: [
        {
          id: 'official-guide',
          title: 'The Official Guide',
          description: 'The official Vue.js documentation. It is the most complete resource for learning about Vue.js.',
          link: 'https://vuejs.org/'
        },
        {
          id: 'google',
          title: 'The Official Guide',
          description: 'The official google documentation. It is the most complete resource for learning about Vue.js.',
          link: 'https://www.google.co.uk/'
        }
      ]
    }
  }
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
