<template>
  <nav-wrapper></nav-wrapper>
  <banner-wrapper></banner-wrapper>
  <div class="wrapper">
    <announce></announce>
    <vision></vision>
    <speaker></speaker>
    <map></map>
    <sponsor></sponsor>
    <staff></staff>
  </div>
  <footer>
    <div class="row">
      2016 phpconftw
    </div>
  </footer>
</template>

<script lang="coffee" type="text/coffeescript">

  module.exports =
    components:
      'nav-wrapper': require './components/Nav'
      'banner-wrapper': require './components/Banner'
      announce: require './components/Announce'
      vision: require './components/Vision'
      speaker: require './components/Speaker'
      map: require './components/Map'
      sponsor: require './components/Sponsor'
      staff: require './components/Staff'

</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import './settings.scss'
  @import '~foundation-sites/scss/foundation'

  +foundation-everything(true)

</style>
