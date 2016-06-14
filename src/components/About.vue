<template>
  <section id="about">
    <div class="row">
      <div class="columns">
        <h4>{{ conf.menu.about }}</h4>
        <div class="about-wrapper">
          <div class="row align-center" v-for="abouts in conf.abouts">
            <avatar v-for="detail in abouts" :detail="detail"></avatar>
          </div>
          <div class="reveal row" id="avatarModel" data-reveal>
            <div class="photo" :style="avatarImg">
            </div>
            <div class="word">
              <h5>{{ detail.name }}</h5>
              <h6 class="lead">{{ detail.brief }}</h6>
              <p>{{ detail.intro }}</p>
            </div>
            <button class="close-button" data-close aria-label="Close modal" type="button">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data: () ->
      return {
      detail:
        name: ""
        brief: ""
        intro: ""
        photo: ""
      }
    computed:
      avatarImg: () ->
        return 'background-image': 'url(' + @detail.photo + ')'
    components:
      avatar: require './Avatar.vue'
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  h4
    text-align: center
  #avatarModel
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
    overflow: auto
    height: 20rem
  h5
    color: blue
  h6
    font-size: 1rem
  p
    font-size: 1.2rem
</style>
