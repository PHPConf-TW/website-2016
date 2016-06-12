<template>
  <section id="sponsor">
    <div class="row">
      <div class="columns">
        <h2>Sponsor</h2>
        <div class="row sponsor-wrapper">
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
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  h2
    text-align: center
  .sponsor-wrapper
    margin: 2rem 10rem
</style>
