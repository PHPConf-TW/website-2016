<template>
  <button type="button">{{ text }}</button>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data:
      text: 'button_text'
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
h1
  color: #42b983
</style>
