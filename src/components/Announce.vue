<template>
  <section id="announce">
    <div class="row">
      <div class="small-12 medium-4 columns">
        <h4>{{ conf.menu.announce }}</h4>
      </div>

      <div class="small-12 medium-5 end columns">
        <ul class="vertical menu" data-accordion-menu>
          <li v-for="item in conf.announce">
            <span class="label" v-bind:class="$index == 0 ? 'warning' : 'primary'">{{ item.date }}</span>
            <a href="#" class="announce-info">{{ item.title }}</a>
            <ul class="nested">
              <li>{{{ item.content }}}</li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    props: ['conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  #announce
    margin-top: 5rem
    margin-bottom: 5rem
    h4
      text-align: right
      +breakpoint(small only)
        text-align: center
    .label
      color: #fff
      font-weight: 600
      width: 4.6rem
      text-align: center
      &.warning
        background: map-get($foundation-palette, warning)
      &.primary
        background: map-get($foundation-palette, primary)
    .is-accordion-submenu-parent > a::after
      border: none
    .is-accordion-submenu-parent[aria-expanded='true']
      &::after
        content: ''
        width: 100%
        height: 1px
        background-color: rgba(202, 202, 202, 0.25)
        display: block
        margin: .5rem 0 1rem
    .is-accordion-submenu-parent[aria-expanded='true'] > a::after
        content: '\00d7'
        color: $medium-gray
        font-size: 1.5rem
        top: -.15rem
        right: 0
        padding: .5rem
        transform: initial
        width: auto
        height: auto
    a.announce-info
      padding-left: 0
      color: $body-font-color
      text-decoration: underline
      padding: .5rem 0
    li
      text-align: left
      display:inline
      padding-bottom: .8rem
    .nested
      margin: 0
      list-style: none
      padding-left: 0

</style>
