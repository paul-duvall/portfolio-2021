<template>
  <div class="main-container">
    <AppNav />
    <Nuxt />
    <AppFooter />
  </div>
</template>

<script>
import AppNav from '../components/AppNav'
import AppFooter from '../components/AppFooter.vue'

export default {
  components: {
    AppFooter,
    AppNav
  }
}
</script>
