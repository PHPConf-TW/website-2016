<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.speaker }}</h4>
        <div class="speaker-wrapper">
          <div class="row align-center" v-for="speakers in conf.speakers">
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
  #speaker
    h4
      text-align: center
      margin-top: 4rem
      margin-bottom: 2rem
</style>
