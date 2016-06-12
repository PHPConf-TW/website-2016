<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h2>Speaker</h2>
        <div class="row">
          <avatar></avatar>
          <avatar></avatar>
          <avatar></avatar>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    components:
      avatar: require './Avatar.vue'
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
</style>
