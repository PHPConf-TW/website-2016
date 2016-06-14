<template>
  <section id="sponsor">
    <div class="row">
      <div class="columns small-12 medium-8 medium-offset-2">
        <h4>{{ conf.menu.sponsor }}</h4>
        <div class="row">
          <diamond-sponsor></diamond-sponsor>
          <silver-sponsor></silver-sponsor>
          <silver-sponsor></silver-sponsor>
          <silver-sponsor></silver-sponsor>
          <silver-sponsor></silver-sponsor>
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
      margin-top: 1.5rem
      margin-bottom: 4rem
    .sponsor-wrapper
      &.silver
        margin: 1.5rem 0 0
      &.silver:nth-child(2n+1)
        padding-left: .6rem
      &.silver:nth-child(2n)
        padding-right: .6rem

    .sponsor
      border: #e4e4e4 solid 1px
      padding: 1.5rem
      box-shadow: 0 0 5px #e8e8e8
      .photo
        background-size: cover
        background-position: center center
        height: 10rem
        +breakpoint(small only)
          height: 8rem
      h6
        color: map-get($foundation-palette, primary)
        font-weight: 500

</style>
