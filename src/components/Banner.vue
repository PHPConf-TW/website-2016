<template>
  <header class="header">
    <div class="banner">
      <div class="row align-center">
        <div class="small-12 column"><img src="http://fakeimg.pl/230x150/?text=logo" alt="PHPConf 2016" class="logo"></div>
        <div class="small-12 column"><p>PHPConf 2016 will hold on Oct 10, Registration will opened on Aug 10.</p></div>
        <div class="small-12 column"><a class="button secondary" href="#" title="Registration">Registration</a></div>
      </div>
    </div>
  </header>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  .banner
    background-image: url('https://c2.staticflickr.com/8/7677/17079728191_ef107ff2f3_h.jpg')
    position: relative
    text-align: center
    background-position: center
    background-size: cover
    height: 400px
    .logo
      padding-top: 80px
      padding-bottom: 20px
    .button
      min-width: 160px
</style>
