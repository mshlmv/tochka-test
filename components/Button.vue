<template>
  <button :href="url" class="button" role="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ["url"]
}
</script>

<style>
</style>
