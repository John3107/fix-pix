<template>
  <div class="input-select">
    <input :list="name" :value="defaultValue">
    <datalist :id="name">
      <option :value="item" v-for="item in data" :key="item"/>
    </datalist>
    <div class="dropdown"></div>
  </div>
</template>

<script>
export default {
  name: 'InputSelect',
  props: ['data', 'defaultValue', 'name']
}
</script>

<style lang="scss" scoped>
.input-select {
  position: relative;
  width: 100%;

  input {
    width: 100%;
    border: 1px solid #D0DAE4;
    border-radius: 3px;
    padding: 14px 12px;
    box-sizing: border-box;
    line-height: 16px;
    font-size: 14px;
    outline: 0;
    height: 44px;
    color: #444;
    position: relative;

    &::-webkit-calendar-picker-indicator {
      display: none !important;
    }
  }

  .dropdown {
    position: absolute;
    top: 20px;
    right: 15px;
    width: 0;
    height: 0;
    border-left: 3px solid transparent;
    border-right: 3px solid transparent;
    border-top: 5px solid #444;
  }
}
</style>

