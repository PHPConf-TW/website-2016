<template lang="html">
    <section id="session">
        <div class="row">
            <h4>{{ conf.menu.session }}</h4>
            <div class="dayswitch-wrapper">
                <div class="small-6 medium-6 columns">
                      <button v-on:click="changeDate(1)" type="button" class="button day-btn" v-bind:class="{'active': isDay1}"><h6>Day 1 (10/29)</h6></button>
                </div>
                <div class="small-6 medium-6 columns">
                      <button v-on:click="changeDate(2)" type="button" class="button day-btn" v-bind:class="{'active': !isDay1}"><h6>Day 2 (10/30)</h6></button>
                </div>
            </div>
        </div>
        <div class="row day" v-bind:class="{'active': isDay1}">
            <div class="columns">
            <div class="table-scroll">
                <table class="main-track">
                    <thead>
                        <tr>
                            <th class="test" width="150">{{ conf.session.day1.maintrack.morning.timeplace }}</th>
                            <th colspan="2">{{ conf.session.day1.maintrack.morning.place }}</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="session in conf.session.day1.maintrack.morning.morningtrack">
                            <td>
                                {{ session.time }}
                            </td>
                            <td colspan="2" v-if=" typeof session.content !== 'string' ">
                                <lecture v-for="lecture in session.content" :lecture="lecture" :conf="conf"></lecture>
                            </td>
                            <td colspan="2" v-else>
                                {{ session.content }}
                            </td>
                        </tr>
                    </tbody>
                <!--  ********************************************************************************************************************************************-->
                    <thead  class=" main-track afternoon-track">
                        <tr>
                            <th width="14%">{{ conf.session.day1.maintrack.afternoon.timeplace }}</th>
                            <th width="43%">{{ conf.session.day1.maintrack.afternoon.place1 }}</th>
                            <th width="43%">{{ conf.session.day1.maintrack.afternoon.place2 }}</th>
                        </tr>
                    </thead>
                    <tbody  class=" main-track afternoon-track">
                        <tr v-for="session in conf.session.day1.maintrack.afternoon.afternoontrack">
                            <td>
                                {{ session.time }}
                            </td>
                            <td colspan="2" v-if=" typeof session.content === 'string' ">
                                {{ session.content }}
                            </td>
                            <td v-else v-for="lecture in session.content">
                                <lecture :lecture="lecture" :conf="conf"></lecture>
                            </td>
                        </tr>

                    </tbody>
                </table>
            </div>
            <div class="table-scroll">
                <table class="qa-track">
                    <thead>
                        <tr>
                            <th width="14%">{{ conf.session.day1.qa.timeplace }}</th>
                            <th>{{ conf.session.day1.qa.place }}</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="session in conf.session.day1.qa.track">
                            <td>
                                {{ session.time }}
                            </td>
                            <td v-if=" typeof session.content !== 'string' ">
                                <lecture v-for="lecture in session.content" :lecture="lecture" :conf="conf"></lecture>
                            </td>
                            <td v-else>
                                {{ session.content }}
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="table-scroll">
                <table class="workshop-track">
                    <thead>
                        <tr>
                            <th width="14%">{{ conf.session.day1.workshop.timeplace }}</th>
                            <th>{{ conf.session.day1.workshop.place }}</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="session in conf.session.day1.workshop.track">
                            <td>
                                {{ session.time }}
                            </td>
                            <td v-if=" typeof session.content !== 'string' ">
                                <lecture v-for="lecture in session.content" :lecture="lecture" :conf="conf"></lecture>
                            </td>
                            <td v-else>
                                {{ session.content }}
                            </td>
                        </tr>
                    </tbody>
                </table>
                </div>
            </div>
        </div>
        <!--  ***********************************************day2*********************************************************************************************-->
        <div class="row day" v-bind:class="{'active': !isDay1}">
            <div class="columns">
            <div class="table-scroll">
                <table class="workshop-track">
                    <thead>
                        <tr>
                            <th width="14%">{{ conf.session.day2.workshop.timeplace }}</th>
                            <th>{{ conf.session.day2.workshop.place }}</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="session in conf.session.day2.workshop.track">
                            <td>
                                {{ session.time }}
                            </td>
                            <td v-if=" typeof session.content !== 'string' ">
                                <lecture v-for="lecture in session.content" :lecture="lecture" :conf="conf"></lecture>
                            </td>
                            <td v-else>
                                {{ session.content }}
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
            </div>
        </div>


    </section>
</template>

<script lang="coffee" type="text/coffeescript">
    module.exports =
        components:
            'lecture': require './Lecture.vue'
        props:
            ['session', 'conf']
        data: () ->
            return {
                isDay1: true
            }
        methods:
            changeDate: (date) ->
                this.isDay1 = (date == 1) ? true : false
                returnL

</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
    @import '../settings.scss'

    #session
        h4
            text-align: center
            margin-top: 4rem
            margin-bottom: 2rem

        .dayswitch-wrapper
            text-align: center
            button
                width: 100%
            div
                margin-bottom: 2rem

        .day-btn
            background: #ccc
            &:hover
                background: map-get($foundation-palette, primary)
            &.active
                background: map-get($foundation-palette, primary)

        .day
            display: none
            &.active
                display: block

        .table-scroll + .table-scroll
            margin-top: 4rem

        .main-track
            thead
                background: mix(map-get($foundation-palette, primary), #000, 85%)
                th
                    text-align: center
                    vertical-align: text-top
            tbody
                tr
                    &:nth-child(even)
                        background: #efefef
                td
                    text-align: center
                    vertical-align: text-top
                    &:first-child
                        color: #fff
                        background-color: map-get($foundation-palette, primary)
                    li:not(:first-child):last-child
                        a
                            i:hover, i:focus
                                color: #516CFF

        .workshop-track, .qa-track
            margin-top: 0
            thead
                background: mix(map-get($foundation-palette, warning), #c3681f, 60%)
                th
                    text-align: center
                    vertical-align: text-top
            tbody
                tr
                    &:nth-child(even)
                        background: #efefef
                td
                    text-align: center
                    vertical-align: text-top
                    &:first-child
                        color: #fff
                        background-color: map-get($foundation-palette, warning)
                    li:not(:first-child):last-child
                        a
                            i:hover, i:focus
                                color: #516CFF


        .afternoon-track
                tr
                    &:nth-child(4n+1)
                        td
                            &:nth-child(3)
                                background-color: #fbfbfb
                    &:nth-child(4n+3)
                        td
                            &:nth-child(2)
                                background-color: #fbfbfb
                            li:not(:first-child):last-child
                                a
                                    i:hover, i:focus
                                        color: #516CFF


        table.main-track, table.workshop-track, table.qa-track
            width: 100%
            min-width: 500px

        table
            thead
                color: #fff
            thead, tbody
                th, td
                    border: 1px solid #fff
            li:not(:first-child):last-child
                a
                    display: inline
                    i
                        margin-top: 1rem
                        margin-bottom: 1rem
                        color: #909091
                        -webkit-transition: color 0.4s



</style>
