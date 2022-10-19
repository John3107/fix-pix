<template>
  <main class="main-container">
    <div v-if="windowWidthWatcher > 1299" class="main-container-itself">
      <billing/>
      <payment/>
    </div>
    <div v-else class="main-container-itself">
      <payment/>
      <billing/>
    </div>
  </main>
</template>

<script>
import Billing from '@/components/body/billing'
import Payment from '@/components/body/payment'

export default {
  name: 'MainView',
  components: {
    Billing,
    Payment
  },
  data() {
    return {
      windowWidthWatcher: window.innerWidth
    }
  }
}
</script>

<style lang="scss" scoped>
.main-container {
  .main-container-itself {
    display: flex;
    width: 100%;
    gap: 18px;
    margin-top: 27px;
    @media(max-width: 1300px) {
      flex-direction: column;
    }
  }
}

</style>

