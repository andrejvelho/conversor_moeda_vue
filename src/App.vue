<template>
  <Home/>
</template>

<script>
import Home from './Home.vue';

export default {
  name: 'App',
  components: {
    Home
  }
};
</script>

<style>

html,
body {
  margin: 0;
  padding: 0;
}

:root {
  --primary: #2a93d5;
  --black: #000000;
  --blackLighter: #9E9E9E;
  --grayLight: #F5F5F5;
  --grayMedium: #e5e5e5; 
  --white: #FFFFFF;
  --frontEnd: #6BD1FF;
  --backEnd: #00C86F;
}

#app {
  min-height: calc(100vh - var(--bodyPaddingTop));
  display: flex;
  flex-direction: column;
}

 @media (max-width: 800px) {
   .linha {
     margin-bottom: 50px;
     display: grid;
   }
}
</style>
