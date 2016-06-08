<template>
  <div class="menu-wrapper">
    <div class="row align-middle">
      <div class="shrink columns title">PHPConf Taiwan 2016</div>
      <nav class="columns text-right">
        <ul>
          <li class="active"><a href="#home">HOME</a></li>
          <li><a href="#vision">VISION</a></li>
          <li><a href="#speaker">SPEAKER</a></li>
          <li><a href="#session">SESSION</a></li>
          <li><a href="#location">LOCATION</a></li>
          <li><a href="#sponsor">SPONSOR</a></li>
          <li><a href="#about">ABOUT</a></li>
        </ul>
      </nav>    
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<style lang="sass?indentedSyntax" type="text/sass">
  @import '../settings.scss'
  .menu-wrapper
    background-color: $dark-gray
    color: $light-gray
    .title
      font-size: 1.1rem
    a
      position: relative
      display: block
      color: $light-gray
      padding: .9rem .55rem
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
        top: 0
        left: 0
    ul
      margin: 0
      font-size: 0.9rem
    li
      display: inline-block
      list-style: none

</style>
