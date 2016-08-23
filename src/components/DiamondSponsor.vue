<template>
  <div class="columns small-12 sponsor-wrapper diamond" v-bind:class="sponsor.more == 'true' ? 'more' : ''">
    <div class="sponsor">
      <div class="row">
        <div class="columns small-12 medium-6">
          <a :href="sponsor.link">
            <div class="photo" :style="sponsorImg"></div>
          </a>
        </div>
        <div class="columns small-12 medium-6">
          <div class="word">
            <h6>{{ sponsor.name }}</h6>
            <p>
              {{{ sponsor.desc }}}
            </p>
            <a href="#" class="moreBtn" @click="openMore">{{conf.more}}</a>
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
    props: ['sponsor', 'conf']
    methods: {
      openMore: (event) ->
        event.preventDefault()
        $(event.target).parents('.diamond').removeClass('more')
      }
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
</style>
