<template>
  <div>
    <nuxt/>
  </div>
</template>

<style>
@import '../assets/fonts/fonts.css';
@import '../assets/css/normalize.css';

html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}

:root {
  --purple-brown: #231f20;
}

body {
  font-family: Geometria, sans-serif;
  font-size: 14px;
  color: var(--purple-brown);
}
</style>
