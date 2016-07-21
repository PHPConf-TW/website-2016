<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.speaker }}</h4>
        <div class="speaker-wrapper align-center">
          <div class="row" v-for="speakers in conf.speakers">
            <avatar v-for="detail in speakers" :detail="detail"></avatar>
          </div>
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
  @import '../settings.scss'

  #speaker
    h4
      text-align: center
      margin-top: 4rem
      margin-bottom: 2rem
    .speaker-wrapper
      text-align: center
      /*padding: 0 1rem*/
      /*+breakpoint(small only)*/
        /*width: 100%*/
        /*padding: 0*/
        /*margin: 0*/
</style>
