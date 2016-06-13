<template>
  <div id="container">
    <nav-wrapper :menu="conf.menu"></nav-wrapper>
    <header-wrapper :header="conf.header"></header-wrapper>
    <div class="wrapper">
      <announce :conf="conf"></announce>
      <vision :conf="conf"></vision>
      <speaker :conf="conf"></speaker>
      <map :conf="conf"></map>
      <sponsor :conf="conf"></sponsor>
      <about :conf="conf"></about>
    </div>
    <footer-wrapper></footer-wrapper>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  require 'foundation-sites/dist/foundation.min.js'

  module.exports =
    data: () ->
      return { conf: {} }
    components:
      'nav-wrapper': require './components/Nav'
      'header-wrapper': require './components/Header'
      'footer-wrapper': require './components/Footer'
      announce: require './components/Announce'
      vision: require './components/Vision'
      speaker: require './components/Speaker'
      map: require './components/Map'
      sponsor: require './components/Sponsor'
      about: require './components/About'
    methods:
      getLang: () ->
        lang = window.location.pathname.split('/')[1]
        index = ['tw', 'en'].indexOf lang
        if index == -1
          lang = 'tw'
        return lang
      changeLang: () ->
        self = @
        lang = @getLang()
        url = '/static/lang/' + lang + '.json'
        $.ajax
          url: url
          dataType: 'text'
          async: false
          success: (data) ->
            self.conf = JSON.parse(data)
            return
          error: (data) ->
            return
        return
    beforeCompile: () ->
      @changeLang()
      console.log 'inited'
      return
    ready: () ->
      $(document).foundation()      
      return

</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import './settings.scss'
  @import '~foundation-sites/scss/foundation'
  @import url('https://fonts.googleapis.com/css?family=Rubik')
  +foundation-everything(true)

  /* Custom Global */
  h4
    font-weight: bold
    font-family: 'Rubik', $body-font-family
    text-transform: capitalize

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
