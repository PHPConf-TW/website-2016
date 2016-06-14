<template>
  <header class="header">
    <div class="banner">
      <div class="banner-img"></div>
      <div class="banner-mask"></div>
      <div class="row align-center inner">
        <div class="small-12 column"><img src="../assets/logo.png" alt="PHPConf 2016" class="logo"></div>
        <div class="small-12 column hide-for-small-only"><p>{{ header.title }}</p></div>
        <div class="small-12 column"><a class="button secondary" href="#" title="Registration">{{ header.registration }}</a></div>
      </div>
    </div>
  </header>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['header']
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  header.header
    margin-top: 3.3rem
  .banner
    position: relative
    text-align: center
    height: 25rem
  .banner-img
    width: 100%
    height: 100%
    background-image: url('../assets/banner.jpg')
    background-position: 0rem 59rem
    background-size: cover
    filter: grayscale(100%)
  .banner-mask
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 0
    width: 100%
    height: 100%
    background: linear-gradient(45deg, rgba(204,204,204,0.2) 0%, rgba(255,255,255,1) 45%, rgba(255,255,255,1) 50%, rgba(254,191,1,.5) 100%) /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#f6f6f6',GradientType=1 )
    /*background: #f39801*/
    /*background: linear-gradient(to bottom, rgba(255,255,255,.2) 10%, rgba(255, 255, 255, 0.4) 40%, rgba(255, 255, 255, 0.5) 80%, rgba(255, 255, 255, .6) 90%)*/
  .inner
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 0
    p
      margin-bottom: 0
  .logo
    padding-top: 4rem
    padding-bottom: 1.25rem
    width: 18rem
  .button
    min-width: 10rem
</style>
