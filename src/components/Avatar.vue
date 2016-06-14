<template>
  <div class="avatar-wrapper">
    <div class="reveal row" id="avatarModel" data-reveal>
      <div class="photo" :style="{ 'background-image': 'url(' + speaker.photo + ')' }">
      </div>
      <div class="word">
        <h5>{{ speaker.name }}</h5>
        <h6 class="lead">{{ speaker.brief }}</h6>
        <p>{{ speaker.intro }}</p>
      </div>
      <button class="close-button" data-close aria-label="Close modal" type="button">
        <span aria-hidden="true">&times;</span>
      </button>
    </div>

    <a class="avatar-model" data-open="avatarModel" :style="{ 'background-image': 'url(' + speaker.photo + ')' }">
      <div class="caption"><span>{{ speaker.name }}</span></div>
    </a>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['speaker']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  .avatar-model
    background-size: cover
    background-position: center center
    height: 8.5rem
    width: 8.5rem
    display: block
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
      span
        font-size: 1rem
        padding: 1rem
        position: relative
        color: white
        top: 40%
        transition: all 0.5s ease-in-out
  .avatar-model:hover
    .caption
      opacity: 0.6
      span
        opacity: 0.8
  .reveal
    width: 60rem
    height: 20rem
    position: relative
    overflow: hidden
  .photo
    float: left
    margin: -1rem 1rem -1rem -1rem
    border: 0
    position: relative
    background-size: cover
    background-position: center center
    width: 25rem
    height: 20rem
    display: block
  .photo:after
    content: ''
    position: absolute
    bottom: 0
    right: 0
    height: 0px
    width: 0px
    border-left: 3rem solid transparent
    border-top: 10rem solid transparent
    border-bottom: 10rem solid white
    border-right: 3rem solid white
  .word
    text-align: justify
    overflow: scroll
    height: 20rem
    h5
      color: blue
    h6
      font-size: 1rem
    p
      font-size: 1.2rem

</style>
