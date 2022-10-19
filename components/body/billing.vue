<template>
  <form class="billing-container">
    <header>
      <h1>Billing information</h1>
      <img :src="require('@/static/info.svg')" alt="info"/>
    </header>
    <main>
      <div class="name-inputs">
        <input-base :label="'First name'" :required="true"/>
        <input-base :label="'Last name'" :required="true"/>
      </div>
      <input-select :data="countriesList" :defaultValue="'Ukraine'" :name="'country'"/>
      <input-base :label="'E-mail'" :required="true" @value="email = $event" :validation="validEmail"/>
      <input-base :label="'Phone number'" :isShowInfo="true"/>
      <div class="payment-method">
        <div class="method-types">
          <div class="type"
               :class="{'selected-method': paymentMethod === 'visa'}"
               @click="paymentMethod = 'visa'">
            <img :src="require('@/static/visa.svg')" alt="visa"/>
          </div>
          <div class="type"
               :class="{'selected-method': paymentMethod === 'paypal'}"
               @click="paymentMethod = 'paypal'">
            <img :src="require('@/static/paypal.svg')" alt="paypal"/>
          </div>
        </div>
        <div class="method-data">
          <input-base :label="'Card number'" :required="true"/>
          <div class="date-cvv">
            <input-select :data="monthList" :defaultValue="'10'" :name="'month'"/>
            <input-select :data="yearsList" :defaultValue="'2022'" :name="'year'"/>
            <input-base :label="'Security code'" :required="true" :isShowInfo="true"/>
          </div>
        </div>
      </div>
    </main>
    <footer>
      <button type="submit">Submit order</button>
    </footer>
  </form>
</template>

<script>
import InputBase from "@/components/facades/input-base"
import InputSelect from "@/components/facades/input-select";

export default {
  name: 'Billing',
  components: {
    InputSelect,
    InputBase
  },
  beforeMount() {
    this.currentMonth = new Date().getMonth() + 1

    this.currentYear = String(new Date()).split(' ')[3]
    if (this.currentMonth < 10) {
      this.currentMonth = '0' + String(this.currentMonth)
    }

    for (let i = 1; i < 13; i++) {
      if (i < 10) this.monthList.push('0' + String(i))
      else this.monthList.push(String(i))
    }

    for (let i = 2000; i < 2051; i++) {
      this.yearsList.push(String(i))
    }
  },
  data() {
    return {
      paymentMethod: 'visa',
      countriesList: ['Ukraine'],
      currentMonth: '',
      currentYear: '',
      monthList: [],
      yearsList: [],
      email: '',
      validEmail: 'isntTouch'
    }
  },
  watch: {
    email(data) {
      const patternEmail = /[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?/;
      if (patternEmail.test(data)) this.validEmail = 'valid'
      else this.validEmail = 'notValid'
    }
  }
}
</script>

<style lang="scss" scoped>
.billing-container {
  display: flex;
  flex-direction: column;
  width: 96.4%;
  height: 542px;
  box-shadow: 0 0 5px #E5E9ED;
  border-radius: 5px;
  padding: 20px;
  box-sizing: border-box;
  @media(max-width: 1300px) {
    width: 100%;
  }
  @media(max-width: 769px) {
    height: 100%;
  }

  header {
    display: inherit;
    align-items: center;
    gap: 10px;
    margin: 0 0 20px;


    h1 {
      margin: 0;
      font-size: 20px;
      line-height: 23px;
    }

    img {
      cursor: pointer;
      width: 16px;
      height: 16px;
    }
  }

  main {
    display: inherit;
    flex-direction: inherit;
    gap: 10px;

    .name-inputs {
      display: inherit;
      justify-content: space-between;
      gap: 16px;
    }

    .payment-method {
      display: inherit;
      flex-direction: inherit;

      .method-types {
        display: inherit;
        justify-content: space-between;
        gap: 14px;

        .type {
          display: inherit;
          justify-content: center;
          align-items: center;
          background: #FFF;
          width: 100%;
          padding: 7px 0 8px;
          border: 1px solid #D0DAE4;
          border-top-left-radius: 10px;
          border-top-right-radius: 10px;
          border-bottom: none;
          z-index: 0;
          cursor: pointer;

          &:first-child {
            img {
              width: 66px;
              height: 15px;
            }
          }
        }

        .selected-method {
          background: #E1E1E1;
          z-index: 2;
        }
      }

      .method-data {
        display: inherit;
        flex-direction: inherit;
        background: #E1E1E1;
        width: 100%;
        padding: 12px 10px 10px;
        border: 1px solid #D0DAE4;
        box-sizing: border-box;
        margin-top: -1px;
        z-index: 1;
        gap: 8px;

        .date-cvv {
          display: inherit;
          @media(max-width: 769px) {
            flex-direction: inherit;
            gap: 8px;
          }
          gap: 16px;
        }
      }
    }
  }

  button {
    width: 100%;
    padding: 21px 0;
    font-size: 18px;
    line-height: 21px;
    font-weight: 500;
    text-transform: uppercase;
    border: none;
    background: #FFC107;
    border-radius: 5px;
    margin-top: 25px;
    cursor: pointer;

    &:hover {
      background: #F7CC51;
    }
  }
}
</style>

