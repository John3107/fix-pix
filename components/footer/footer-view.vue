<template>
  <footer class="footer-container">
    <span>Privacy Policy | Terms and Conditions | Refund Policy</span>
    <span>© PayPro Global, Inc. 2021</span>
  </footer>
</template>

<script>
export default {
  name: 'FooterView'
}
</script>

<style lang="scss" scoped>
.footer-container {
  display: flex;
  justify-content: space-between;
  margin: 20px 0 17px;
  font-size: 13px;
  color: #666C70;
  line-height: 18px;
  @media(max-width: 769px) {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
}

</style>

