<template>
  <div class="reveal" id="avatarModel" data-reveal>
    <div class="photo">
      <img src="//placehold.it/250x200">
    </div>
    <div class="word">
      <h4>Gavin Bates</h4>
      <h6 class="lead">PHPConf Host</h6>
      <p>I'm a cool paragraph that lives inside of an even cooler modal. Wins! I'm a cool paragraph that lives inside of an even cooler modal. Wins!I'm a cool paragraph that lives inside of an even cooler modal. Wins!I'm a cool paragraph that lives inside of an even cooler modal. Wins!I'm a cool paragraph that lives inside of an even cooler modal. Wins!I'm a cool paragraph that lives inside of an even cooler modal. Wins!</p>
    </div>
    <button class="close-button" data-close aria-label="Close modal" type="button">
      <span aria-hidden="true">&times;</span>
    </button>
  </div>

  <a class="avatar-model" data-open="avatarModel">
    <div class="caption"><span>Caption</span></div>
  </a>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  .avatar-model
    background-image: url('http://fakeimg.pl/200x120/?text=photo')
    background-size: cover
    background-position: center center
    width: 8.5rem
    height: 8.5rem
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
      transition: all 0.2s ease-in-out
      span
        font-size: 1rem
        padding: 1rem
        position: relative
        color: white
        top: 40%
        transition: all 0.2s ease-in-out
  .avatar-model:hover
    .caption
      opacity: 0.6
      span
        opacity: 0.8
  .reveal
    width: 50em
    max-height: 200px
  .photo
    float: left
    margin: -1em 1em -1em -1em
    border: 0
    position: relative
  .photo:after
    content: ''
    position: absolute
    bottom: 0
    right: 0
    height: 0px
    width: 0px
    border-left: 30px solid transparent
    border-top: 100px solid transparent
    border-bottom: 100px solid white
    border-right: 30px solid white
  .word
    text-align: justify
    h4
      color: blue

</style>
