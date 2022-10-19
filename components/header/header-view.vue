<template>
  <header class="header-container">
    <img :src="require('static/logo.svg')" alt="logo"/>
    <div class="icons-selects">
      <img :src="require('static/select-language.svg')" alt="icon select language"/>
      <img :src="require('static/select-currency.svg')" alt="icon select currency"/>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderView'
}
</script>

<style lang="scss" scoped>
.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 71px;
  @media(max-width: 769px) {
    flex-direction: column;
    height: 100%;
  }

  .icons-selects {
    display: inherit;
    gap: 10px;
  }
}

</style>

