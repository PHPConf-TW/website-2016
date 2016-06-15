<template>
  <div class="columns small-12 sponsor-wrapper diamond">
    <div class="sponsor">
      <div class="row">
        <div class="columns small-12 medium-6">
          <div class="photo" :style="sponsorImg"></div>
        </div>
        <div class="columns small-12 medium-6">
          <div class="word">
            <h6>{{ sponsor.name }}</h6>
            <p>
              {{ sponsor.desc }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="coffee" type="text/coffeescript">
  module.exports =
    data: () ->
      return {
        sponsorImg:
          'background-image': 'url(' + @sponsor.photo + ')'
        }
    props: ['sponsor']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
</style>
