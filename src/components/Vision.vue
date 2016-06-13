<template>
  <section id="vision">
    <div class="row">
      <div class="small-12 large-8 columns content">
        <div class="row">
          <div class="small-12 large-10 large-offset-2 columns">
            <h4>{{ conf.menu.vision }}</h4>
            {{{ conf.vision.content }}}
          </div>
        </div>
      </div>
      <div class="small-12 large-4 columns photo align-self-middle">
        <img src="../assets/joshlockhart.jpeg" alt="PHPConf" class="hide-for-small-only hide-for-medium-only">
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  #vision
    .row
      max-width: 100%
    .content
      background-color: $light-gray
      padding: 5rem 4rem 3.5rem
    .photo
      margin-left: -5rem
      img
        box-shadow: 0 0 .3rem rgba(0, 0, 0, 0.3)
        border: .06rem solid rgba(179, 179, 179, 0.73)
        width: 17.8rem
</style>
