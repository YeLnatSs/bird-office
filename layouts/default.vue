<template>
  <div>
    <Header/>
    <Nuxt />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: "Circular";
  src: url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.eot");
  src: url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.eot?#iefix") format("embedded-opentype"),
      url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.woff2") format("woff2"),
      url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.woff") format("woff"),
      url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.ttf") format("truetype"),
      url("//db.onlinewebfonts.com/t/2b344f641cb4ebd77656f35154457c2d.svg#Circular Std Black") format("svg");
}

@font-face {
  font-family: "sf";
  src: url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.eot");
  src: url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.eot?#iefix") format("embedded-opentype"),
      url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.woff2") format("woff2"),
      url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.woff") format("woff"),
      url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.ttf") format("truetype"),
      url("//db.onlinewebfonts.com/t/5c24022ee697267b3f2bda61de84f5ad.svg#SF UI Text") format("svg");
}

@font-face {
  font-family: "CircularBook";
  src: url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.eot");
  src: url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.eot?#iefix") format("embedded-opentype"),
      url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.woff2") format("woff2"),
      url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.woff") format("woff"),
      url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.ttf") format("truetype"),
      url("//db.onlinewebfonts.com/t/860c3ec7bbc5da3e97233ccecafe512e.svg#Circular Std Book") format("svg"); }

html {
  font-family:
  'sf',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 62.5%;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.container {
  @media screen and (min-width: 1200px) {
    max-width: 1440px;
  }
}

.mw1034 {
  @media screen and (min-width: 1200px) {
    max-width: 1034px;
    margin: 0 auto;
  }
}
</style>
