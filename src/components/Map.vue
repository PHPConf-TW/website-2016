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
        { saturation: -50 }
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
    .map-content
      position: absolute
      z-index: 1
      background-color: #fff
      padding: 3.5rem
      max-width: 20rem
      right: 15%
      top: 4.8rem
      .location-name
        color: map-get($foundation-palette, primary)
        font-size: 1.2rem
      ul
        margin-top: 1.2rem
        font-size: .9rem
</style>
