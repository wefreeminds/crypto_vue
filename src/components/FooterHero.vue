<template>
  <div class="hero-foot">
    <footer class="footer">
      <div class="mobile-footer">
        <div class="made-by" :class="{'hide': isOpenedInIFrame}">Freed by <a href="https://github.com/wefreeminds" target="_blank">Israel Wilson</a> | <icon name="calendar" height="12"></icon> 2019</div>
        <p class="wallet-tag">BTC <span>3GADF3JbQnDwvVpdwjio2F79UkmvY4eAzm</span></p>
        <p class="wallet-tag">ETH <span >0x0Af24eE26F3d681ABE101974334cfAcbC762a22c</span></p>
      </div>
      <div class="desktop-footer" :class="{'hide': isOpenedInIFrame}">
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'footerHero',
  props: {},
  data () {
    return {
      isOpenedInIFrame: false
    }
  },
  created () {
    if (window.self !== window.top) {
      this.isOpenedInIFrame = true
    }
  }
}
</script>

<style scoped lang="scss">
$small: 590px;
$medium: 768px;
$large: 1024px;

.footer {
  background-color: transparent;
  padding: 3rem 1.5rem 0rem;
  position: relative;

  @media screen and (max-width: $small) {
    padding-top: 60px;
  }

  .mobile-footer {
    display: none;
    font-size: 15px;
    font-weight: 400;
    position:absolute;
    bottom: 15px;
    left: 0;
    right: 0;
    margin: 0 auto;

    a {
      color: #fd6721;
    }

    @media screen and (max-width: $small) {
      display: block;
    }

    .wallet-tag {
      font-size: 9px;
      font-weight: 600;

      span {
        color: #00d1b2;
      }
    }
  }

  .desktop-footer {
    display: block;

    .button {
      float: right;
      padding: 10px;
      margin-bottom: 10px;
    }

    @media screen and (max-width: $medium) {
      display: none;
    }
  }
}

.hide {
  display: none !important;
}
</style>
