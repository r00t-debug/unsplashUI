<template>
  <div>
    <Navbar />
    <div class="spacer" />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
import Footer from '@/components/Footer'
export default {
  components: {
    Navbar,
    Footer
  }
}
</script>

<style>
  .spacer {
    height: 52px;
  }
</style>
