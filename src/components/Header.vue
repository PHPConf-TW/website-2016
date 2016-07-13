<template>
  <header class="header">
    <div class="banner">
      <div class="banner-img"></div>
      <div class="banner-mask"></div>
      <div class="row align-center inner">
        <div class="small-12 column banner-content">
          <!--<img src="../assets/logo.png" alt="PHPConf 2016" class="logo">-->
          <h1>PHPConf Taiwan 2016</h1>
          <div class="content">
            <p class="hide-for-small-only">{{ header.title }}</p>
            <a class="button secondary" href="#" title="Registration" v-if="header.isShow == 'true'">{{ header.registration }}</a>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script lang="coffee" type="text/coffeescript">
  imagesLoaded = require 'imagesloaded'
  module.exports =
    props: ['header']
    methods:
      loadHeader: () ->
        imagesLoaded '.banner-img', { background: true }, () ->
          console.log 'header'
          $('.banner-img').addClass 'show-banner'
        return
      loadLogo: () ->
        imagesLoaded '.logo', () ->
          console.log 'logo'
          $('.banner-content').addClass 'show-logo'
        return
    ready: () ->
      @loadHeader()
      @loadLogo()
      return
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  header.header
    margin-top: 3.3rem
    h1
      font-size: 4rem
      font-weight: bold
      position: absolute
      width: 100%
      top: 12rem
      transition: all 1s ease-in-out .5s
  .banner
    position: relative
    text-align: center
    height: 30rem
  .banner-img
    width: 100%
    height: 100%
    background-image: url('../assets/banner1.jpg')
    background-position: 0rem 59rem
    background-size: cover
    filter: grayscale(100%)
    opacity: 0
    transition: opacity 1s ease-in-out
    &.show-banner
      opacity: 1
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
      padding-bottom: 1.5rem
  .inner:nth-child(2)
    color: red
  .logo
    padding-top: 6rem
    padding-bottom: 1.25rem
    width: 20rem
    opacity: 0
    transition: all 1s ease-in 1s
  .content
    position: absolute
    width: 100%
    top: 19rem
  .banner-content.show-logo
    .logo
      opacity: 1
    /*h1*/
      /*opacity: 0*/
  .button
    min-width: 12rem
    font-size: 1rem
</style>
