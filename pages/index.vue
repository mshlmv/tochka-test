<template>
  <div class="wrap">
    <section class="banner">
      <div class="container">
        <h1 class="banner__title">Тестовое задание</h1>
        <p class="banner__text">На экранах до 1024px показывать CSS-анимацию. При клике на кнопку плавный scroll до следующего блока.</p>
        <div class="banner__button">
          <Button splash="true" :options="buttonOptions">Подробнее</Button>
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
    width: 100%;
    padding: 0 36px;
    margin: 0 auto;
  }

  section .container {
    margin-top: 48px;
  }
  .banner {
    margin-bottom: 65px;
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
  }
  .banner__text {
    font-size: 14px;
    font-weight: bold;
    line-height: 1.43;
    margin-bottom: 48px;
    @media (min-width: 768px) {
      font-size: 16px;
      line-height: 1.5;
    }
  }
  .section-title {
    font-size: 26px;
    line-height: 1.23;
    margin-top: 0;

    @media (min-width: 768px) {
      font-size: 40px;
      line-height: 1.2;
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
      display: flex;
      flex-flow: row;
      flex-wrap: wrap;
    }
  }
</style>
