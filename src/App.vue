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
    <modal :detail="detail" :type="type"></modal>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  require 'foundation-sites/dist/foundation.min.js'

  module.exports =
    data: () ->
      return {
        lang: 'tw',
        conf: {},
        type: '',
        detail:
          name: ""
          brief: ""
          intro: ""
          photo: ""
      }
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
      modal: require './components/Modal'
    methods:
      getLang: () ->
        lanRegx = /lang=(en|tw)/
        res = window.location.search.match lanRegx
        if res != null
          window.sessionStorage["lang"] = res[1]
        lang = window.sessionStorage["lang"]
        index = ['tw', 'en'].indexOf lang
        if index != -1
          @lang = lang
        return
      changeLang: () ->
        self = @
        url = '/static/lang/' + @lang + '.json'
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
      @getLang()
      @changeLang()
      return
    ready: () ->
      $(document).foundation()
      $('#container').addClass @lang
      return
    events:
      'open-avatar': (detail, type) ->
        @detail = detail
        @type = type
        return

</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import './settings.scss'
  @import '~foundation-sites/scss/foundation'
  @import '~motion-ui/dist/motion-ui.min.css'
  /*@import url('https://fonts.googleapis.com/css?family=Rubik')*/
  /*@import url('https://fonts.googleapis.com/css?family=Francois+One')*/

  +foundation-everything($global-flexbox)

  /* Custom Global */
  *:focus
    outline: none

  html, body
    word-spacing: 0.05rem

  h4
    font-weight: bold
    font-family: 'Rubik', $body-font-family
    text-transform: capitalize
    +breakpoint(small only)
      text-align: center
      margin-bottom: 1.5rem

  section
    margin-top: 2.5rem
    margin-bottom: 3rem

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
