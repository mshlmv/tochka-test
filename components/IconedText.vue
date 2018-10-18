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

<style>
.iconed-text {
  display: flex;
  align-items: center;
}
.iconed-text__icon {
  margin-right: 24px;
}
.iconed-text__text {
  color: #000;
}
</style>
