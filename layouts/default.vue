<template>
  <div>
    <TheHeader/>
    <nuxt/>
    <TheFooter/>
  </div>
</template>
<script>
import TheHeader from '@/components/TheHeader/TheHeader'
import TheFooter from '@/components/TheFooter/TheFooter'
export default {
  components: {
    TheHeader,
    TheFooter
  }
}
</script>

<style>
html {
  font-family: Lato, 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
nuxt {
  display: 100%;
}
TheFooter {
  position: fixed;
  left: 0;
  width: 100;
  height: 10px;
  text-align: center;
}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
</style>
