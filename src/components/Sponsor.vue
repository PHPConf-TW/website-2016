<template>
  <section id="sponsor">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.sponsor }}</h4>
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
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  h4
    text-align: center
</style>
