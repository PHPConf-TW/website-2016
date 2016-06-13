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
        <ul class="menu align-right">
          <li class="active"><a href="#home">{{ menu.home }}</a></li>
          <li><a href="#announce">{{ menu.announce }}</a></li>
          <li><a href="#vision">{{ menu.vision }}</a></li>
          <li><a href="#speaker">{{ menu.speaker }}</a></li>
          <li><a href="#session">{{ menu.session }}</a></li>
          <li><a href="#location">{{ menu.location }}</a></li>
          <li><a href="#sponsor">{{ menu.sponsor }}</a></li>
          <li><a href="#about">{{ menu.about }}</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['menu']
</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import '../settings.scss'
  .menu-wrapper
    background-color: $dark-gray
    color: $light-gray
    .title-bar
      background: inherit
      .title
        padding: .307rem .55rem
    .top-bar
      background-color: inherit
      .title
        +breakpoint(small only)
          display: none
      .menu
        +breakpoint(small only)
          display: block
        li
          +breakpoint(small only)
            display: block
            width: 100%
            border-top: 1px solid #505050
            padding: .5rem
    .menu
      background-color: inherit
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
