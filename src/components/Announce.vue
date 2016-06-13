<template>
  <section id="announce">
    <div class="row announce-section">
          <div class="small-offset-1 small-10 large-offset-3 large-1 columns">
            <h4>{{ conf.menu.announce }}</h4>
          </div>

          <div class="small-offset-1 small-10 large-5 columns">
            <ul class="vertical menu" data-accordion-menu>
              <li>
                <span class="label warning">AUG 08</span>
                <a href="#" class="announce-info">This registration will open, please focus on our latest news.</a>
                <ul class="menu vertical nested">
                  <div>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</div>
                </ul>
              </li>
              <li>
                <span class="label primary">JUNE 11</span>
                <a href="#" class="announce-info">This registration will open, please focus on our latest news.</a>
                <ul class="menu vertical nested">
                  <li>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</li>
                </ul>
              </li>
              <li>
                <span class="label primary">MAY 08</span>
                <a href="#" class="announce-info">This registration will open, please focus on our latest news.</a>
                <ul class="menu vertical nested">
                  <li>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</li>
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
  .announce-section
    margin-top: 30px
    margin-bottom: 50px

  .label
    color: #fff
    margin-top: 7px
    font-weight: 600;
    &.warning
      background: #f39801
    &.primary
      background: #516cff

  .is-accordion-submenu-parent > a::after
    border: none
  .is-accordion-submenu-parent[aria-expanded='true']
    margin-top: 20px
    margin-bottom: 20px
    padding-top: 5px
    padding-bottom: 5px
    border-top: 1px solid #d4d4d4
    border-bottom: 1px solid #d4d4d4

  .is-accordion-submenu-parent[aria-expanded='true'] > a::after
     content: '\00d7'
     color: #8d8d8d
     font-size: 30px
     top: 15px


  .announce-info
    font-size: 0.5rem
    padding-left: 0
    color: #000
    text-decoration: underline

  li
    text-align: left
    display:inline

  .menu.nested
    margin-left: 0

</style>
