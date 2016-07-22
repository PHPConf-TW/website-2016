<template>
  <div class="reveal row {{ type }}" id="avatarModel"  data-reveal data-animation-in="fade-in" data-animation-out="fade-out">
    <div class="photo" :style="avatarImg">
    </div>
    <div class="word">
      <div class="title">
        <h5>{{ detail.name }}</h5>
        <h6 class="lead">{{{ detail.brief }}}</h6>
      </div>
      <div class="content">
        {{{ detail.intro }}}
      </div>
    </div>
    <button class="close-button" data-close aria-label="Close modal" type="button">
      <span aria-hidden="true">&times;</span>
    </button>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    computed:
      avatarImg: () ->
        return 'background-image': 'url(' + @detail.photo + ')'
    props: ['detail', 'type']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  #avatarModel
    width: 50rem
    height: 22rem
    position: relative
    overflow: hidden
    padding: 2rem
    +breakpoint(small only)
      width: auto
      overflow: auto
    h5
      color: map-get($foundation-palette, primary)
      +breakpoint(small only)
        font-size: 1.5rem
    h6
      font-size: 1rem
      +breakpoint(small only)
        font-size: 1rem
    .photo
      float: left
      margin: -2rem 1rem -1rem -2rem
      border: 0
      position: relative
      background-size: cover
      background-position: center center
      width: 22rem
      height: 22rem
      display: block
      +breakpoint(small only)
        width: 100%
        height: 11rem
        margin: 2rem 0 0 0
    .photo:after
      content: ''
      position: absolute
      bottom: 0
      right: 0
      height: 0px
      width: 0px
      border-left: 3rem solid transparent
      border-top: 11rem solid transparent
      border-bottom: 11rem solid white
      border-right: 3rem solid white
      +breakpoint(small only)
        border: 0
    .word
      text-align: justify
      overflow: auto
      height: 20rem
      +breakpoint(small only)
        padding-top: 2rem
        height: auto
        width: 100%
    .close-button
      color: #ddd
      font-size: 3rem
      right: 1.2rem
    .close-button:hover
      color: #ccc
      transition: all 0.5s ease-in-out
    .content
      font-size: .9rem
      padding-right: 3rem
      overflow: scroll
      height: 11rem
      +breakpoint(small only)
        padding: 0
        height: auto
    &.about
      width: 36rem
      height: 18rem
      +breakpoint(small only)
        width: auto
      .photo
        width: 18rem
        height: 18em
        +breakpoint(small only)
          width: 100%
          height: 11rem
          margin: 2rem 0 0 0
      .photo:after
        border: 0
      .word
        padding: 1rem

</style>