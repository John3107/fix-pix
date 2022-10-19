<template>
  <div class="payment-container">
    <header>
      <div class="head">
        <span>PRODUCT</span>
        <span>PRICE</span>
      </div>
      <div class="description">
        <div class="description-main">
          <img :src="require('@/static/product.svg')" alt="product"/>
          <div class="main">
            <span class="main-title">Test Product</span>
            <span class="main-description">Product description</span>
            <span class="main-link">Auto-renewal</span>
          </div>
        </div>
        <div class="price">100.00 USD</div>
      </div>
      <div class="vat">
        <div class="vat-itself">
          <img :src="require('@/static/info.svg')" alt="info"/>
          <div class="info">VAT (20.00%): <span>20.00</span> USD</div>
        </div>
      </div>
      <div class="total"><span>TOTAL: 120.00</span><span class="usd"> USD</span></div>
    </header>
    <main>
      <p>Do not hesitate to contact our CUSTOMER CARE CENTER for more information about payment
        and delivery.<br>
        Please state the order ID from the confirmation email as a reference so that we can assist you
        efficiently.</p>
      <p>24/7 English phone support for online payment related issues:</p>
      <div class="call">
        <img :src="require('@/static/call.svg')" alt="call"/>
        <div class="phone-numbers">
          <div class="number"><span>+ 1-888-317-4868</span> (Toll free)</div>
          <div class="number"><span>+ 1-647-977-7769</span> (International)</div>
        </div>
      </div>
      <p>By submitting your Order, you acknowledge that you are purchasing from PayPro Global (PayPro
        <br>Global, Inc., PayPro Europe Limited or PayPro U.S. Inc.), an authorized e-Commerce reseller.</p>
      <p>Once the transaction is complete, your contact information will be shared with the product vendor for ongoing
        support purposes.</p>
    </main>
    <footer>
      <img :src="require('@/static/dss-certified.svg')" alt="dss certified" class="dss-certified"/>
      <img :src="require('@/static/trusted-site.svg')" alt="trusted site" class="trusted-site"/>
      <img :src="require('@/static/norton-secured.svg')" alt="norton secured" class="norton-secured"/>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'Payment'
}
</script>

<style lang="scss" scoped>
.payment-container {
  width: 100%;

  .head {
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid #CDD8DD;
    font-size: 9px;
    color: #9FA7AB;
    font-weight: 700;
    line-height: 11px;
    padding-bottom: 3px;
  }

  .description {
    display: flex;
    justify-content: space-between;
    margin: 5px 0 8px;

    .description-main {
      display: inherit;
      gap: 20px;
      margin-top: 3px;

      .main {
        display: inherit;
        flex-direction: column;

        .main-title {
          font-weight: 600;
          font-size: 14px;
          line-height: 16px;
          color: #25272C;
        }

        .main-description {
          font-weight: 400;
          font-size: 13px;
          line-height: 15px;
          color: #666C70;
          margin: 3px 0;
        }

        .main-link {
          font-weight: 400;
          font-size: 13px;
          line-height: 15px;
          color: #2F76F6;
          margin-top: 3px;
        }
      }
    }

    .price {
      color: #333;
      font-size: 14px;
      line-height: 16px;
      font-weight: 600;
    }
  }

  .vat {
    display: flex;
    justify-content: flex-end;
    border: 1px solid #CDD8DD;
    border-left: none;
    border-right: none;
    padding: 7.5px 0 9.5px;

    .vat-itself {
      display: inherit;
      align-items: center;

      .info {
        margin-left: 1px;
        font-weight: 500;
        font-size: 12px;
        line-height: 14px;

        span {
          font-weight: 600;
        }
      }
    }
  }

  .total {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    color: #80C600;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    white-space: pre;
    margin-top: 10px;

    .usd {
      font-size: 12px;
      line-height: 14px;
    }
  }

  main {
    display: flex;
    flex-direction: column;
    margin: 17px 2px;
    gap: 10px;

    p {
      margin: 0;
      color: #666C70;
      font-size: 13px;
      line-height: 18px;
    }

    .call {
      display: inherit;
      justify-content: flex-start;
      align-items: center;

      img {
        width: 36px;
        height: 33px;
      }

      .phone-numbers {
        display: inherit;
        flex-direction: column;
        margin-left: 8px;

        .number {
          color: #666C70;
          font-size: 13px;
          line-height: 18px;

          span {
            font-weight: 700;
          }
        }
      }
    }
  }

  footer {
    display: flex;
    justify-content: center;
    margin-top: 42px;
    gap: 15px;
    @media(max-width: 769px) {
      flex-direction: column;
      align-items: center;
    }

    .dss-certified {
      width: 112px;
      height: 54px;
    }

    .trusted-site {
      width: 112px;
      height: 47px;
    }

    .norton-secured {
      width: 115px;
      height: 58px;
    }
  }
}

</style>

