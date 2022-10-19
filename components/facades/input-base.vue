<template>
  <div class="input-base">
    <input type="text" v-model="value"
           :style="{
      borderColor: label === 'E-mail' ?
      validation === 'isntTouch' ? null : validation === 'valid' ? '#80C600' : '#E02222'
      : null
    }"/>
    <label v-if="!value">{{ label }}<span v-if="required"> *</span></label>
    <img v-if="isShowInfo" :src="require('@/static/info.svg')" alt="info"/>
  </div>
</template>

<script>
export default {
  name: 'InputBase',
  props: ['label', 'required', 'isShowInfo', 'validation'],
  data() {
    return {
      value: ''
    }
  },
  watch: {
    value(data) {
      this.$emit('value', data)
    }
  }
}
</script>

<style lang="scss" scoped>
.input-base {
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
  }

  label {
    position: absolute;
    color: #9A9A9A;
    font-size: 14px;
    top: 16px;
    left: 14px;

    span {
      content: " *";
      color: #E02222;
    }
  }

  img {
    width: 16px;
    height: 16px;
    position: absolute;
    top: 14px;
    right: 12px;
    cursor: pointer;
  }
}
</style>

