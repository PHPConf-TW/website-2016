<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.speaker }}</h4>
        <div class="row speaker-wrapper">
          <avatar class="columns"></avatar>
          <avatar class="columns"></avatar>
          <avatar class="columns"></avatar>
          <avatar class="columns"></avatar>
          <avatar class="columns"></avatar>
          <avatar class="columns"></avatar>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    components:
      avatar: require './Avatar.vue'
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  h4
    text-align: center
  .speaker-wrapper
    margin: 2rem 10rem
</style>
