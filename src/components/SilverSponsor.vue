<template>
    <div class="columns small-6">
        <div class="silver-wrapper ">
            <div class="word">
                <h5>Silver Sponsor</h5>
            </div>
            <div class="photo" style="background-image: url('http://fakeimg.pl/200x120/?text=photo')">

            </div>
        </div>
    </div>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
    @import '../settings.scss'
    .silver-wrapper
        border: #ddd solid 1px
        padding: 2rem
        box-shadow: 0 0 10px #ddd
        margin: 1rem 0
    .photo
        background-size: cover
        background-position: center center
        height: 10rem
        display: block
    .word
        text-align: center
        h5
            color: blue
</style>
