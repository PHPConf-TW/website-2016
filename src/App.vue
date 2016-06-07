<template>
  <nav></nav>
  <header>
    <div class="banner">
      <div class="row">
        <h1>Banner</h1>
      </div>
    </div>
  </header>
  <div class="wrapper">
    <Announce></Announce>
    <Vision></Vision>
    <Speaker></Speaker>
    <Map></Map>
    <Sponsor></Sponsor>
    <Staff></Staff>
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
      Announce: require './components/Announce'
      Vision: require './components/Vision'
      Speaker: require './components/Speaker'
      Map: require './components/Map'
      Sponsor: require './components/Sponsor'
      Staff: require './components/Staff'

</script>

<style lang="sass?indentedSyntax" type="text/sass">

  @import '~foundation-sites/scss/foundation.scss'
  @include foundation-flex-classes
  @include foundation-flex-grid

  html
    height: 100%

</style>
