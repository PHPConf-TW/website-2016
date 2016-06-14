<template>
  <section id="about">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.about }}</h4>
        <div class="about-wrapper">
          <div class="row align-center" v-for="abouts in conf.abouts">
            <avatar v-for="detail in abouts" :detail="detail"></avatar>
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
  #about
    h4
      text-align: center
      margin-top: 4rem
      margin-bottom: 2rem
</style>
