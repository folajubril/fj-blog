<template>
  <section 
    class="container- main" 
    background="~/static/slider.jpg" >
    <div class="jumbotron">
      <h1 class="align-center title">Welcome to my little big world</h1>
      <hr>
      <p class="subtitle">Here you can read my blog posts and contact me <button 
        class="btn btn-danger" 
        type="submit">
        <nuxt-link 
        to="/about">Here</nuxt-link></button> to learn more</p>
    </div>
  </section>
</template>

<script>
import slider from '~/static/slider.jpg'
export default {
  components: {
    slider
  }
}
</script>

<style scoped>
.main {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: url(../static/slider.jpg);
}
.jumbotron {
  background: rgba(0, 0, 0, 0.0001);
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 75px;
  color: #39ff14;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 30px;
  color: #ff6700;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
