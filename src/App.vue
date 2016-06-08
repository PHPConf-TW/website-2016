<template>
  <nav-wrapper></nav-wrapper>
  <header>
    <div class="banner">
      <div class="row">
        <h1>Banner</h1>
      </div>
    </div>
  </header>
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
