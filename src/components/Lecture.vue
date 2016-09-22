<template>
    <div class="lecture-wrapper">
        <div class="row">
            <div class="small-12 medium-8 columns title">{{ lecture.title }}</div>
            <div class="small-12 medium-4 columns speaker">{{ lecture.speaker }}</div>
        </div>
        <div v-if="lecture.outline != ''" class="row">
            <ul class="vertical menu" data-accordion-menu>
              <li>
                <a class="outline">{{ lecture.outline }}</a>
                <ul class="menu vertical nested description">
                  <li>{{ lecture.detail }}</li>
                  <li><a href="{{ lecture.slideshare }}"><i class="fa fa-2x fa-slideshare" aria-hidden="true"></i></a><a href="{{ lecture.youtube }}"><i class="fa fa-2x fa-youtube" aria-hidden="true"></i></a></li>
                </ul>
              </li>
            </ul>
        </div>
    </div>
</template>

<script lang="coffee" type="text/coffeescript">
    module.exports =
        props: ['lecture', 'conf']
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
    @import '../settings.scss'

    .lecture-wrapper
        padding-left: 1rem
        padding-right: 1rem
        .title
            text-align: left
            padding: 0
            padding-left: 1rem
            font-size: 105%

        .speaker
            text-align: right
            padding: 0
            padding-right: 1rem
        .outline
            line-height: 1.6
            text-align: left
            padding-right: 1.6rem
            color: #323232
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
                    -webkit-transition: color 0.4s
                i.fa-slideshare:hover, i.fa-slideshare:focus
                    color: #4875B4
                i.fa-youtube:hover, i.fa-youtube:focus
                    color: #FF3333





    .is-accordion-submenu-parent > a::after
            top: 1.2rem
            border-color: #909091 transparent transparent
            right: 0.9rem

</style>
