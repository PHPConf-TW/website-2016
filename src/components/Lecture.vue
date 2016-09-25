<template>
    <div class="lecture-wrapper">
        <div class="clearfix">
            <div class="small-12 medium-8 columns title">{{ lecture.title }}</div>
            <div class="small-12 medium-4 columns speaker">{{ lecture.speaker }}</div>
        </div class="clearfix">
        <div v-if="lecture.outline != ''">
            <div class="small-12">
              <ul class="vertical menu content" v-bind:class="{'active': isMore(lecture.detail), 'open': openMenu}" >
                {{lecture.menu}}
                <li>
                  <a class="outline" v-on:click="clickOutline()">{{{ lecture.outline }}}</a>
                  <ul class="menu vertical nested description">
                    <li>{{ lecture.detail }}</li>
                    <li><a v-if="lecture.slideshare != ''" href="{{ lecture.slideshare }}"><i class="fa fa-2x fa-slideshare" aria-hidden="true"></i></a><a v-if="lecture.youtube != ''" href="{{ lecture.youtube }}"><i class="fa fa-2x fa-youtube" aria-hidden="true"></i></a></li>
                  </ul>
                </li>
              </ul>
            </div>
        </div>
    </div>
</template>

<script lang="coffee" type="text/coffeescript">
    module.exports =
        props: ['lecture', 'conf'],
        data: () ->
          return {
            openMenu: false
          }
        methods:
          isMore: (detail) ->
            return (detail != '') ? true : false
          clickOutline: () ->
            this.openMenu = !this.openMenu
            return
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
    @import '../settings.scss'

    .lecture-wrapper
      .title
        text-align: left
        padding: 0
        padding-left: 1rem
        font-size: 105%
        +breakpoint(small only)
          padding: 0
      .speaker
        text-align: right
        padding: 0
        padding-right: 1rem
        +breakpoint(small only)
          padding: 0
          text-align: left
          &:before
            content: ''
            display: inline-block
            height: 1px
            width: 1rem
            background: #949494
            margin-bottom: .3rem
            margin-right: .4rem
      .content.active
        .outline
          cursor: pointer
        .outline:after
          content: ''
          display: block
          width: 0
          height: 0
          border: 6px inset
          border-color: #909091 transparent transparent
          border-top-style: solid
          border-bottom-width: 0
          position: absolute
          top: 1.2rem
          margin-top: -4px
          right: 0.9rem
          +breakpoint(small only)
            right: -0.5rem
        &.open .outline:after
          transform-origin: 50% 50%
          transform: scaleY(-1)
        .description
          max-height: 0
          overflow: hidden
          transition: max-height ease .4s
        &.open .description
          max-height: 500px
      .outline
        cursor: default
        line-height: 1.6
        text-align: left
        padding-right: 1.6rem
        color: #323232
        position: relative
        +breakpoint(small only)
          padding-left: 0
          padding-right: 5px
      .description
        text-align: left
        color: #000
        padding-right: 1.6rem
      div
        vertical-align: text-top
      li:first-child
        color: #323232
      li:not(:first-child):last-child
        a
          display: inline
          i
            margin-top: 1rem
            margin-bottom: 1rem
            color: #909091
            transition: color 0.4s
          i.fa-slideshare:hover, i.fa-slideshare:focus
            color: #4875B4
          i.fa-youtube:hover, i.fa-youtube:focus
            color: #FF3333
</style>
