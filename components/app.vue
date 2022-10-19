<template>
  <div class="app-container">
    <header-view/>
    <main-view/>
    <footer-view/>
  </div>
</template>

<script>
import HeaderView from '@/components/header/header-view'
import MainView from '@/components/body/main-view'
import FooterView from "@/components/footer/footer-view";

export default {
  name: 'App',
  components: {
    FooterView,
    HeaderView,
    MainView
  }
}
</script>

<style lang="scss" scoped>
.app-container {
  font-family: 'Roboto', sans-serif;
  margin: 0 10.5% 0 10.2% !important;
}

</style>

