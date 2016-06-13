<template>
  <div class="diamond-wrapper row">
    <div class="photo columns" style="background-image: url('http://fakeimg.pl/200x120/?text=photo')">

    </div>
    <div class="word columns">
      <h5>Diamond Sponsor</h5>
      <p>
        Code in your favorite language and IDE – .NET, NodeJS, PHP, Python, or Java – to build web apps and APIs faster than ever. Be more agile with continuous integration using Visual Studio Team Services or GitHub and with live-site debugging. Easily scale applications on-demand with high availability.
      </p>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'
  .diamond-wrapper
    border: #ddd solid 1px
    padding: 2rem
    box-shadow: 0 0 10px #ccc
    margin: 1rem
  .photo
    float: left
    background-size: cover
    background-position: center center
    display: block
  .word
    text-align: justify
    h5
      color: blue
    p
      font-size: 1rem
      margin-bottom: 0
</style>
