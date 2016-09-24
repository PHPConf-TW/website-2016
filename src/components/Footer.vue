<template>
  <footer class="footer">
      <ul>
        <li><a href="http://2015.phpconf.tw/">2015</a></li>
        <li><a href="http://2014.phpconf.tw/">2014</a></li>
        <li><a href="http://2013.phpconf.tw/">2013</a></li>
        <li><a href="http://2012.phpconf.tw/">2012</a></li>
        <li><a href="http://2011.phpconf.tw/">2011</a></li>
      </ul>
      2016 © PHPConf Taiwan
  </footer>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  .footer
    margin-top: 1rem
    margin-bottom: 2rem
    color: $medium-gray
    font-size: .9rem
    text-align: center
    ul
      margin-left: 0
      margin-bottom: .5rem
    ul li
      display: inline-block
      line-height: .8rem
    li + li
      border-left: 1px solid #ccc
      padding-left: .5rem
    a
      color: $medium-gray
      font-size: .9rem
      &:hover
        color: darken($medium-gray, 20%)
</style>
