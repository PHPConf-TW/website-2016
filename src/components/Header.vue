<template>
  <header class="header">
    <div class="banner">
      <div class="banner-mask">
        <div class="banner-img"></div>
      </div>
      <div class="row align-center inner">
        <div class="small-12 column banner-content" v-bind:class="header.isShow == 'false' ? 'no-btn' : ''">
          <h1>PHPConf Taiwan 2016<img src="../assets/logo2.png" alt="PHPConf 2016" class="logo"></h1>
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
  @import '../settings.scss'

  header.header
    margin-top: 3.3rem
    h1
      font-size: 3.5rem
      font-weight: bold
      transition: opacity 1s ease-in-out
      color: #f5f5f5
      opacity: 1
      /*background-color: rgba(0, 0, 0, 0.3)*/
      display: inline-block
      margin: 8rem auto 0
      padding: 1rem
      +breakpoint(small only)
        font-size: 2rem
  .banner-content.no-btn
    h1
      margin: 10.5rem auto 0
      +breakpoint(small only)
        margin-top: 6rem
  .banner-content
    text-align: center
  .banner
    position: relative
    text-align: center
    height: 30rem
    overflow: hidden
    +breakpoint(small only)
      height: 20rem
  .banner-img
    height: 30rem
    background-image: url('../assets/banner.jpg')
    background-position: center 60%
    background-size: cover
    opacity: 0
    transition: opacity 1s ease-in-out
    background-repeat: no-repeat
    transform: scale(1.03)
    filter: blur(3px) contrast(110%) brightness(50%) sepia(0.8) hue-rotate(-15deg)
    +breakpoint(small only)
      height: 20rem
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
