<template>
  <section id="speaker">
    <div class="row">
      <div class="columns">
        <h2>Speaker</h2>
        <avatar></avatar>
        <avatar></avatar>
        <avatar></avatar>
        <div class="reveal" id="exampleModal1" data-reveal>
          <h1>Awesome. I Have It.</h1>
          <p class="lead">Your couch. It is mine.</p>
          <p>I'm a cool paragraph that lives inside of an even cooler modal. Wins!</p>
          <button class="close-button" data-close aria-label="Close modal" type="button">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <p><a data-open="exampleModal1">Click me for a modal</a></p>
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
