<template>
  <div class="container">
    <section class="banner">
      <h1 class="banner__title">Тестовое задание</h1>
      <p class="banner__text">На экранах до 1024px показывать CSS-анимацию. При клике на кнопку плавный scroll до следующего блока.</p>
      <div class="banner__button">
        <Button url="#next" class="button_splash">Подробнее</Button>
      </div>
    </section>
    <section class="icons">
      <IconedText icon="card">Банковские карты</IconedText>
      <IconedText icon="message">Мессенджер</IconedText>
      <IconedText icon="ibank">Интернет-банк</IconedText>
      <IconedText icon="ewallet">Электронный кошелёк</IconedText>
      <IconedText icon="phone">Баланс телефона</IconedText>
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
  }
}
</script>

<style>

</style>
