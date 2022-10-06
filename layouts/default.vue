<template>
  <div>
    <Header />

    <div class="main">
      <nuxt/>
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from '~/components/Footer'
import Header from '~/components/Header'
export default {
  components:{
    Header, Footer
  }
}
</script>

<style>
body{
  background-color: #171e28 !important;
}
</style>
