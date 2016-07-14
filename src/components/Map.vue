<template>
  <section id="map">
    <div class="map-content">
      <div class="location-name">{{ conf.location.name }}</div>
        <div class="location-addr">{{ conf.location.address }}</div>
        <ul>
          <li>{{ conf.location.description1 }}</li>
          <li>{{ conf.location.description2 }}</li>
        </ul>
    </div>
    <div id="map-wrapper"></div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  googleMapsLoader = require('google-maps')

  styleArray = [
    {
      featureType: "all"
      stylers: [
        { hue: "#81BEF7" },
        { saturation: -80 }
      ]
    }
  ]
  center = {lat: 25.037437, lng: 121.432141}
  latLng = {lat: 25.0378358, lng: 121.4305338}
  options =
    center: center,
    scrollwheel: false
    styles: styleArray
    zoom: 17

  googleMapsLoader.load (google) ->
    map = new google.maps.Map document.getElementById('map-wrapper'), options
    marker = new google.maps.Marker
      map: map
      position: latLng
    return

  module.exports =
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  #map
    position: relative
    #map-wrapper
      max-width: 100%
      height: 30rem
      background-color: #fefefe
      +breakpoint(small only)
        height: 15rem

  .tw
    .map-content
      padding: 3.5rem
      max-width: 20rem
      top: 4.8rem
  .en
    .map-content
      max-width: 25rem
      padding: 2rem
      top: 5.3rem
      .location-name
        font-size: 1rem
        padding-bottom: .2rem
      .location-addr
        font-size: .9rem

  .tw .map-content, .en .map-content
    position: absolute
    z-index: 1
    background-color: #fff
    right: 15%
    +breakpoint(small only)
      position: relative
      top: 0
      margin: 0
      max-width: 100%
      right: 0
      padding: 2rem 1.4rem 1rem
      background-color: #fbfbfb
      border-top: 1px solid #f5f5f5
    .location-name
      color: map-get($foundation-palette, primary)
      font-size: 1.2rem
    ul
      margin-top: 1.2rem
      font-size: .9rem
</style>
