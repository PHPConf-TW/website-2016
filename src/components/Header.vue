<template>
  <header class="header">
    <div class="banner">
      <div class="banner-img"></div>
      <div class="banner-mask"></div>
      <div class="row align-center inner">
        <div class="small-12 column banner-content" v-bind:class="header.isShow == 'false' ? 'no-btn' : ''">
          <!--<img src="../assets/logo.png" alt="PHPConf 2016" class="logo">-->
          <h1>PHPConf Taiwan 2016<img src="../assets/logo2.png" alt="PHPConf 2016" class="logo1"></h1>
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
          $('.banner-img').addClass 'show-banner'
        return
      loadLogo: () ->
        imagesLoaded '.logo', () ->
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
      transition: all 1s ease-in-out .5s
      color: #f5f5f5
      font-family: 'Francois One'
      opacity: 1
      /*background-color: rgba(0, 0, 0, 0.3)*/
      display: inline-block
      margin: 8rem auto 0
      padding: 1rem
  .banner-content.no-btn
    h1
      margin: 9rem auto 0
  .banner-content
    text-align: center
  .banner
    position: relative
    text-align: center
    height: 30rem
  .banner-img
    width: 110%
    height: 29.8rem
    background-image: url('../assets/banner.jpg')
    background-position: center 60%
    background-size: cover
    filter: grayscale(65%) blur(4px) contrast(150%) brightness(80%)
    opacity: 0
    transition: opacity 1s ease-in-out
    background-repeat: no-repeat
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
    /*background: linear-gradient(45deg, rgba(204,204,204,0.2) 0%, rgba(255,255,255,1) 45%, rgba(255,255,255,1) 50%, rgba(254,191,1,.5) 100%) /!* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ *!/*/
    /*filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#f6f6f6',GradientType=1 )*/
    background: rgba(52, 66, 95, 0.24)
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
  .logo1
    width: 5rem
    position: relative
    top: .5rem
    left: 0rem
  .content
    width: 100%
    font-family: sans-serif, Georgia
    font-weight: bold
    color: #eee
  .banner-content.show-logo
    .logo
      opacity: 1
    /*h1*/
      /*opacity: 0*/
  .button
    min-width: 12rem
    font-size: 1rem
</style>
