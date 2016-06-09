<template>
  <nav-wrapper></nav-wrapper>
  <header-wrapper></header-wrapper>
  <div class="wrapper">
    <announce></announce>
    <vision></vision>
    <speaker></speaker>
    <map></map>
    <sponsor></sponsor>
    <staff></staff>
  </div>
  <footer-wrapper></footer-wrapper>
</template>

<script lang="coffee" type="text/coffeescript">
  require 'foundation-sites/dist/foundation.min.js'
#  require 'foundation-sites/js/foundation.core.js'
#  require 'foundation-sites/js/foundation.util.keyboard.js'
#  require 'foundation-sites/js/foundation.util.box.js'
#  require 'foundation-sites/js/foundation.util.triggers.js'
#  require 'foundation-sites/js/foundation.util.mediaQuery.js'
#  require 'foundation-sites/js/foundation.util.motion.js'
#  require 'foundation-sites/js/foundation.util.nest.js'
#  require 'foundation-sites/js/foundation.reveal.js'
#  require 'foundation-sites/js/foundation.accordionMenu.js'

  module.exports =
    components:
      'nav-wrapper': require './components/Nav'
      'header-wrapper': require './components/Header'
      'footer-wrapper': require './components/Footer'
      announce: require './components/Announce'
      vision: require './components/Vision'
      speaker: require './components/Speaker'
      map: require './components/Map'
      sponsor: require './components/Sponsor'
      staff: require './components/Staff'
    ready: () ->
      $(document).foundation()

</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import './settings.scss'
  @import '~foundation-sites/scss/foundation'
  @import url('https://fonts.googleapis.com/css?family=Rubik')
  +foundation-everything(true)

  /* Custom Global */
  h4
    font-weight: bold
    font-family: 'Rubik', $body-font-family

  .button
    border-radius: 3px
    &:hover
      background-color: #3f69cc
    &.disabled
      color: #d4d4d4
      opacity: 0.9
      background-color: #3f69cc

  .button.secondary
    ＆:hover
      background-color: #dd991d
    &.disabled
      background-color: #F39801

  .button.alert
    &:hover
      background-color: #df3500
    &.disabled
      background-color:  #df3500
</style>
