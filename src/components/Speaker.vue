<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.speaker }}</h4>
        <avatar></avatar>
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
</style>
