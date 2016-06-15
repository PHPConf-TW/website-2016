<template>
  <div class="avatar-wrapper">
    <a class="avatar-model" data-open="avatarModel" @click="openAvatar" :style="avatarImg">
      <div class="caption"><span>{{ detail.name }}</span></div>
    </a>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data: () ->
      return {
        avatarImg:
          'background-image': 'url(' + @detail.photo + ')'
      }
    props: ['detail']
    methods: {
      openAvatar: () ->
        @$dispatch 'open-avatar', @detail
    }
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  .avatar-wrapper
    margin: 1rem
    +breakpoint(small only)
      width: 40%
  .avatar-model
    background-size: cover
    background-position: center center
    height: 8.5rem
    width: 8.5rem
    display: block
    +breakpoint(small only)
      width: 100%
      height: 12rem
      margin: 0
    .caption
      position: absolute
      display: inherit
      background: rgba(0,0,0,0.8)
      color: white
      opacity: 0
      width: 8.5rem
      height: 8.5rem
      text-align: center
      transition: all 0.5s ease-in-out
      +breakpoint(small only)
        width: 40%
        height: 12rem
        margin: 0
      span
        font-size: 1.2rem
        padding: 1rem
        position: relative
        color: white
        top: 40%
        transition: all 0.5s ease-in-out
        +breakpoint(small only)
          font-size: 1.4rem
  .avatar-model:hover
    .caption
      opacity: 0.6
      span
        opacity: 0.8
</style>
