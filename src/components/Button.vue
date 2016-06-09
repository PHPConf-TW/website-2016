<template>
  <div class="row">
    <h1>------- Button area -------</h1>
  </div>

  <div class="row">
    <div class="small-4 large-4 columns">
      <button type="button"  class="button">{{ buttonb }}</button>
    </div>
    <div class="small-4 large-4 columns">
      <button type="button"  class="button secondary">{{ buttony }}</button>
    </div>
    <div class="small-4 large-4 columns">
      <button type="button"  class="button alert">{{ buttonr }}</button>
    </div>
  </div>
  <div class="row">
    <div class="small-4 large-4 columns">
      <button type="button"  class="button disabled">{{ buttonb }}</button>
    </div>
    <div class="small-4 large-4 columns">
      <button type="button"  class="button secondary disabled">{{ buttony }}</button>
    </div>
    <div class="small-4 large-4 columns">
      <button type="button"  class="button alert disabled">{{ buttonr }}</button>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data: () ->
      return {
        buttonb: 'Button'
        buttony: 'Hightlight'
        buttonr: 'Danger'
      }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  .button
    border-radius: 3px
    &:hover
      background-color: #3f69cc
    &.disabled
      color: #d4d4d4
      opacity: 0.9
      background-color: #3f69cc

  .button.secondary
    ＆:hover
      background-color: #dd991d
    &.disabled
      background-color: #F39801

  .button.alert
    &:hover
      background-color: #df3500
    &.disabled
     background-color:  #df3500
</style>
