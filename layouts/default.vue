<template>
    <nuxt/>
</template>
<script>
export default {
  head () {
    return {
      script: [
        { src: 'https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js' }
      ],
      link: [
        { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css?family=Roboto' }
      ]
    } 
  }
}
</script>
<style lang="scss">
@import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
*, *::before, *::after{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
a{
    text-decoration: none;
    color: inherit ;
}
html{
    font-family: 'Roboto' sans-serif;
    background: #f5f5f5;
}
body{
   background: rebeccapurple;
}
</style>
