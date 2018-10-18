<template>
  <div class="iconed-text">
    <div class="iconed-text__icon">
      <img :src=" '/icons/'+ icon +'.svg' ">
    </div>
    <div class="iconed-text__text">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["icon"]
}
</script>

<style lang="scss">
.iconed-text {
  display: flex;
  align-items: center;

}
.iconed-text__icon {
  margin-right: 24px;

  img {
    display: block;
  }
}
.iconed-text__text {
  color: #000;
  font-size: 14px;

  @media (min-width: 768px) {
    font-size: 16px;
  }
  @media (min-width: 1200px) {
    font-size: 18px;
  }
}
</style>
