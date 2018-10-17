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
</style>
