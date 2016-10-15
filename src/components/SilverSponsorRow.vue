<template>
  <div class="row">
    <silver-sponsor v-for="sponsor in sponsorRow" :sponsor="sponsor" :conf="conf"></silver-sponsor>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    components:
      'silver-sponsor': require './SilverSponsor.vue'
    props: ['sponsorRow', 'conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
</style>
