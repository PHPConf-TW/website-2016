<template>
  <section id="map">
    <div class="map-content">
      <div class="location-name">輔仁大學國璽樓</div>
        <div class="location-addr">新北市新莊區中正路510號</div>
        <ul>
          <li>輔大校門進入直行至最後端至中美堂，左轉第2棟有玻璃帷幕之新大樓即為國璽樓</li>
          <li>自輔大貴子門進入，右轉第一棟大樓即為國璽樓。(現場將有場務人員舉牌引導方向)</li>
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
      top: 5rem
      .location-name
        color: map-get($foundation-palette, primary)
        font-size: 1.2rem
      ul
        margin-top: 1.2rem
        font-size: .9rem
</style>
