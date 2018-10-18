<template>
  <div class="wrap">
    <section class="banner">
      <div class="container">
        <h1 class="banner__title">Тестовое задание</h1>
        <p class="banner__text">На экранах до 1024px показывать CSS-анимацию. При клике на кнопку плавный scroll до следующего блока.</p>
        <div class="banner__button">
          <Button splash="true" :options="buttonOptions">Подробнее</Button>
        </div>

        <div class="banner__image">
          <div class="banner__image-wrap">
            <img src="~assets/images/splash.png" class="banner__image-splash">
            <img src="~assets/images/wallet.png" class="banner__image-wallet">
            <img src="~assets/images/shadow.png" class="banner__image-shadow">
          </div>
        </div>
      </div>
    </section>
    <section class="icons">
      <div class="container">
        <h2 class="section-title">Колонки с иконками</h2>
        <div class="iconed-list">
          <IconedText icon="card">Банковские карты</IconedText>
          <IconedText icon="message">Мессенджер</IconedText>
          <IconedText icon="ibank">Интернет-банк</IconedText>
          <IconedText icon="ewallet">Электронный кошелёк</IconedText>
          <IconedText icon="phone">Баланс телефона</IconedText>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  import Button from '~/components/Button.vue'
  import IconedText from '~/components/IconedText.vue'

  export default {
    components: {
      Button,
      IconedText
    },
    data() {
      return {
        buttonOptions: {
          duration: 1000,
          toTarget: '.icons'
        }
      }
    }
  }
</script>

<style lang="scss">
  .container {
    width: 288px;
    margin: 0 auto;
    position: relative;

    @media (min-width: 768px) {
      width: 576px;
    }
    @media (min-width: 992px) {
      width: 864px;
    }
    @media (min-width: 1200px) {
      width: 992px;
    }
  }

  section .container {
    margin-top: 48px;

    @media (min-width: 768px) {
      margin-top: 80px;
    }
  }
  .banner {
    padding-bottom: 65px;

    @media (min-width: 992px) {
      overflow: hidden;
      padding-top: 130px;
      padding-bottom: 130px;

      .container {
        margin-top: 0;
      }
    }

    @media (min-width: 992px) and (max-height: 1080px) and (min-height: 768px) {
      height: 100vh;
      display: flex;
      align-items: center;
      padding-bottom: 0;
      padding-top: 0;
    }
  }
  .banner__title {
    font-size: 32px;
    line-height: 1.25;
    color: #000;
    margin-top: 0;
    margin-bottom: 48px;

    @media (min-width: 768px) {
      font-size: 48px;
      line-height: 1.17;
    }
    @media (min-width: 1200px) {
      font-size: 70px;
      line-height: 1.11;
    }
  }
  .banner__text {
    font-size: 14px;
    font-weight: bold;
    line-height: 1.43;
    margin-bottom: 48px;
    @media (min-width: 768px) {
      font-size: 16px;
      line-height: 1.5;
      max-width: 430px;
    }
    @media (min-width: 1200px) {
      font-size: 18px;
      line-height: 1.56;
      max-width: 480px;
    }
  }
  .banner__image {
    display: none;

    @media (min-width: 992px) {
      display: flex;
      align-items: center;
      position: absolute;
      z-index: -1;
      right: -30%;
      top: -100px;
      height: 100%;
    }

  }

  .banner__image-wrap {
    position: relative;
    width: 800px;
    height: 800px;

    img {
      position: absolute;
    }
  }

  .banner__image-wallet {
    animation: bounce 5s infinite ease-in-out;
  }
  .banner__image-shadow {
    animation: shadow 5s infinite ease-in-out;
  }

  @keyframes bounce {
    0% { transform: translateY(-25px)  }
    50% { transform: translateY(30px) }
    100% { transform: translateY(-25px) }
  }
  @keyframes shadow {
    0% { opacity: .5}
    50% { opacity: 1}
    100% { opacity: .5}
  }

  .section-title {
    font-size: 26px;
    line-height: 1.23;
    margin-top: 0;

    @media (min-width: 768px) {
      font-size: 40px;
      line-height: 1.2;
    }
    @media (min-width: 1200px) {
      font-size: 56px;
      line-height: 1.14;
    }
  }

  .icons {
    &::before {
      content: '';
      display: block;
      width: 100%;
      height: 9px;
      background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), var(--purple-brown));
      opacity: .1;
    }
  }

  .iconed-list {
    margin-top: 32px;

    @media (min-width: 768px) {
      margin-top: 48px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 1fr 1fr 1fr;
      grid-column-gap: 20px;
      grid-row-gap: 32px;
      justify-items: stretch;
      align-items: stretch;
    }

    @media (min-width: 992px) {
      margin-bottom: 110px;
    }
  }
</style>
