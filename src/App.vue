<template>
  <div id="app">
    <div class="bg">
      <Title></Title>
      <Live></Live>
      <Comments></Comments>
      <Footer></Footer>
    </div>
  </div>
</template>

<script>
import Title from './components/Title'
import Live from './components/Live/Live'
import Comments from './components/Comments/Comments.vue'
import Footer from "./components/footer";

export default {
  name: 'App',
  components: {
    Title,
    Live,
    Comments,
    Footer
  }
}
</script>

<style lang='less'>
  @import "./fonts/font.css";
 .bg{
   width: 1920px;
   height: 2926px;
  background: url(./assets/bg.png) no-repeat top center;
}
body{
  margin: 0;
}
</style>
