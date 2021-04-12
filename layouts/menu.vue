<template>
  <div>
    <TheHeaderMenu />
    <Nuxt />
  </div>
</template>

<style lang="scss">
$text-global-color: #343a40; // gray-800

html {
  font-family:
    'Mulish', sans-serif,
    /* 'Source Sans Pro', */
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  
}

body {
  // background-color: rgb(175, 240, 218);
  font-family: 'Mulish', sans-serif;
  color: $text-global-color;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>