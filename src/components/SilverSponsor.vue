<template>
  <div class="columns small-6 sponsor-wrapper silver" v-bind:class="sponsor.more == 'true' ? 'more' : ''">
    <div class="sponsor">
      <div class="word">
        <h6 class="text-center">{{ sponsor.name }}</h6>
      </div>
      <a :href="sponsor.link">
        <div class="photo" :style="sponsorImg">
        </div>
      </a>
      <p>
        {{{ sponsor.desc }}}
      </p>
      <a href="#" class="moreBtn" @click="openMore">{{conf.more}}</a>
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
    props: ['sponsor', 'conf', 'index']
    methods: {
      openMore: (event) ->
        event.preventDefault()
        $(event.target).parents('.silver').removeClass('more')
    }
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
</style>
