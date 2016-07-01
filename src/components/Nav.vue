<template>
  <div class="menu-wrapper">
    <div class="title-bar" data-responsive-toggle="menu" data-hide-for="medium">
      <div class="title">PHPConf Taiwan 2016</div>
      <button class="menu-icon" type="button" data-toggle></button>
    </div>
    <div class="top-bar row" id="menu">
      <div class="top-bar-left">
        <div class="title">PHPConf Taiwan 2016</div>
      </div>
      <div class="top-bar-right">
        <ul class="dropdown menu align-right" data-dropdown-menu>
          <li class="active"><a href="#home">{{ menu.home }}</a></li>
          <li><a href="#announce">{{ menu.announce }}</a></li>
          <li><a href="#vision">{{ menu.vision }}</a></li>
          <li><a href="#speaker">{{ menu.speaker }}</a></li>
          <li><a href="#session">{{ menu.session }}</a></li>
          <li><a href="#location">{{ menu.location }}</a></li>
          <li><a href="#sponsor">{{ menu.sponsor }}</a></li>
          <li><a href="#about">{{ menu.about }}</a></li>
          <li>
            <a href="#">{{ menu.language }}</a>
            <ul class="menu vertical">
              <li><a v-on:click="changeLang('en')">English</a></li>
              <li><a v-on:click="changeLang('tw')">中文</a></li>
            </ul>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['menu']
    methods:
      changeLang: (lang) ->
        window.sessionStorage["lang"] = lang
        window.location.reload()
        return
</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import '../settings.scss'
  .menu-wrapper
    background-color: $dark-gray
    color: $light-gray
    position: fixed
    top: 0
    z-index: 2
    width: 100%
    box-shadow: 0 2px 5px rgba(0,0,0,0.3)
    border-bottom: 1px solid #424242
    .title-bar
      .title
        padding: .307rem 0
      .menu-icon
        // outline: none
    .top-bar
      .title
        +breakpoint(small only)
          display: none
      .dropdown.menu
        +breakpoint(small only)
          display: block
        > li
          +breakpoint(small only)
            display: block
            width: 100%
            border-top: 1px solid #505050
            padding: .5rem
      .dropdown.menu > li.is-dropdown-submenu-parent > a
        &::after
          border-color: $light-gray transparent transparent 
      .dropdown.menu.align-right .is-dropdown-submenu.first-sub
        background-color: rgba(74, 74, 74, 0.9)
        color: $light-gray
        border: 0
        margin-top: .636rem
        z-index: 0
        +breakpoint(small only)
          position: relative
          top: 0
      .is-dropdown-submenu > li
        +breakpoint(small only)
          padding: .5rem 0
    .title
      font-size: 1.1rem
    a
      position: relative
      display: block
      color: $light-gray
      &:hover
        color: $white
    .active a
      color: $light-gray
      background-color: inherit
      &:before
        content: ''
        position: absolute
        display: block
        width: 100%
        height: .3rem
        background-color: $light-gray
        top: -0.5rem
        left: 0
        +breakpoint(small only)
          display: none
    ul
      margin: 0
      font-size: 0.9rem
      text-transform: uppercase
    li
      display: inline-block
      list-style: none

</style>
