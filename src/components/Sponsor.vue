<template>
  <section id="sponsor">
    <div class="row">
      <div class="columns small-12 medium-10 medium-offset-1">
        <h4>{{ conf.menu.sponsor }}</h4>
        <div class="row">
          <diamond-sponsor v-for="sponsor in conf.diamondsponsors" :sponsor="sponsor" :conf="conf"></diamond-sponsor>
        </div>
        <div class="row">
          <silver-sponsor v-for="sponsor in conf.silversponsors" :sponsor="sponsor" :conf="conf"></silver-sponsor>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    components:
      'diamond-sponsor': require './DiamondSponsor.vue'
      'silver-sponsor': require './SilverSponsor.vue'
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import '../settings.scss'

  #sponsor
    h4
      text-align: center
      margin-top: 4rem
      margin-bottom: 2rem
    .sponsor-wrapper
      float: left
      &.silver
        margin: 1.5rem 0 0
      &.silver:nth-child(2n)
        padding-left: .6rem
      &.silver:nth-child(2n+1)
        padding-right: .6rem
      &.diamond
        margin-top: 1.5rem
    .sponsor
      border: #e4e4e4 solid 1px
      padding: 1.5rem
      box-shadow: 0 0 5px #e8e8e8
      .photo
        background-position: center center
        background-repeat: no-repeat
        background-size: contain
        height: 10rem
        +breakpoint(small only)
          height: 8rem
      h6
        color: map-get($foundation-palette, primary)
        font-weight: 500
      p
        text-align: justify
      .moreBtn
        display: none
    .diamond.more
      .word p
        height: 6.5rem
        overflow: hidden
      .moreBtn
        display: block
</style>
