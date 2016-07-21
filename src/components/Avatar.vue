<template>
  <div class="avatar-wrapper">
    <div class="avatar-inner">
      <a class="avatar-model" data-open="avatarModel" @click="openAvatar" :style="avatarImg">
        <div class="caption"><span>{{ detail.name }}</span></div>
      </a>
      <a class="avatar-mask"></a>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  imagesLoaded = require 'imagesloaded'
  module.exports =
    data: () ->
      return {
        avatarImg:
          'background-image': 'url(' + @detail.photo + ')'
      }
    props: ['detail', 'type']
    methods: {
      openAvatar: () ->
        @$dispatch 'open-avatar', @detail, @type
    }
    ready: () ->
      imagesLoaded '.avartar-model', { background: true }, () ->
        $('.avatar-model').addClass 'show-avatar'
        return
      return
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  $avatar-width: 10.5rem + 2rem

  .avatar-wrapper
    position: relative
    background: #fff
    height: $avatar-width
    display: inline-block
    width: $avatar-width
    padding: .1rem 1.4rem
    &:nth-child(odd)
      padding-right: .2rem
    &:nth-child(even)
      padding-left: .2rem
    +breakpoint(small only)
      width: 50%
      height: 12rem
      flex-wrap: wrap
  .single .avatar-wrapper
    +breakpoint(small only)
      width: 100%
      padding: 0 1.4rem
  .avatar-inner
    width: 100%
    height: 100%
    position: relative
  .avatar-model
    background-size: cover
    background-position: center center
    height: 100%
    width: 100%
    display: block
    position: relative
    z-index: 1
    opacity: 0
    transition: opacity 0.5s ease-in-out
    &.show-avatar
      opacity: 1
    +breakpoint(small only)
      margin: 0
    .caption
      position: absolute
      display: inherit
      background: rgba(0,0,0,0.8)
      color: white
      opacity: 0
      width: 100%
      height: 100%
      text-align: center
      transition: opacity 0.5s ease-in-out
      +breakpoint(small only)
        margin: 0
        opacity: 0.8
        span
          opacity: 0.8
      span
        padding: 1rem
        position: relative
        color: white
        top: 40%
        transition: opacity 0.5s ease-in-out
  .avatar-model:hover
    .caption
      opacity: 0.8
      span
        opacity: 0.8
  .avatar-mask
    background-color: #ddd
    height: 100%
    width: 100%
    position: absolute
    top: 0
    left: 0
    z-index: 0.5
    +breakpoint(small only)
      margin: 0
</style>
