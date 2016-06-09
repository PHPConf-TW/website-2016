<template>
  <div class="row">
    <h1>------- Table area -------</h1>
  </div>
  <div class="small-12  large-offset-2 large-8 columns">
    <table>
      <thead class="test">
      <tr>
        <th class="primary" width="200">Header</th>
        <th class="primary dark">Header Dark</th>
      </tr>
      </thead>
      <tbody>
      <tr>
        <td class="primary dark">AM 9:00</td>
        <td>Example Session Subject</td>
      </tr>
      <tr>
        <td class="primary" >AM 10:00</td>
        <td>Example Session Subject</td>
      </tr>
      <tr>
        <td class="primary dark">AM 11:00</td>
        <td>Example Session Subject.</td>
      </tr>
      <tr>
        <td class="primary">AM 12:00</td>
        <td>Example Session Subject.</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  table
    td
      border: 1px solid #fff
      padding: 0.6rem 1rem
    th
      border: 1px solid #fff
      padding:  0.6rem 1rem
    .primary
      background: #516CFF
      color: #fff
      &.dark
        background: #3f69cc

</style>
