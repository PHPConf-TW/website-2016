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
#  require 'foundation-sites/js/foundation.reveal.js'

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

  +foundation-everything(true)

  /* Custom Global */
  h4
    font-weight: bold


</style>
