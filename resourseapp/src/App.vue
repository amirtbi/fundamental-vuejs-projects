<template>
<section>
  
  <the-header title="Remember"></the-header>

  <the-resources></the-resources>
  <the-footer :main-links="mainLinks"></the-footer>
</section>
</template>

<script>

import TheHeader from "./components/layouts/TheHeader.vue";
import TheFooter from './components/layouts/TheFoorter.vue';
import TheResources from './components/LearningResource/TheResources.vue'

// import BaseSlideMenu from './components/UI/BaseSlideMenu.vue';
export default {
  components: {
   
    TheHeader,
    TheFooter,
    TheResources,

  
    // BaseSlideMenu
  },
  data() {
    return {
      mainLinks:["HOME","ABOUT US","MORE"],
      
      
    };
  },

  methods:{
   
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Karla:wght@300&family=Roboto&display=swap');


* {
  box-sizing: border-box;
}
#app{
  position: relative;
}
body {
  margin: 0;
  scroll-behavior: smooth;
  height: 100vh;
  position:relative;
  
}
html {
  font-family: "Roboto", sans-serif;
  scroll-behavior: smooth;
  height: 100vh;
}
a {
  text-decoration: none;
 
}
</style>
