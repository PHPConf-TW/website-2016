<template>
  <section id="vision">
    <div class="row">
      <div class="small-12 large-8 columns content">
        <div class="row">
          <div class="small-12 large-10 large-offset-2 columns">
            <h4>Vision</h4>
            <p>今年是 PHP 重要的一年，PHP 7 的推出將大幅的提昇 PHP 的執行效率，讓 PHP 在更多元的應用場景得以伸展拳腳。</p>
            <p>今年我們將議程聚焦在效能與大型架構上，並請到 PHP 的作者 Rasmus 與 PHP 核心成員的 Laruance 來為我們提供第一手的 PHP 資訊並分享極致效能的議題。同時我們也請到了各界的高手來分享實戰經驗，議程橫跨了 Big Data、水平擴充、軟體架構、ORM、Async I/O 等各種核心領域，想要更深入瞭解 PHP 進階技術，或是如何掌控大型網站架構的朋友，千萬別錯過這些高手們交流的機會。</p>
          </div>
        </div>
      </div>
      <div class="small-12 large-4 columns photo align-self-middle">
        <img src="http://fakeimg.pl/250x250/?text=photo" alt="PHPConf" class="hide-for-small-only hide-for-medium-only">
      </div>
    </div>
  </section>
</template>

<script lang="coffee" type="text/coffeescript">
</script>

<style lang="sass?indentedSyntax" type="text/sass" scoped>
  @import '../settings.scss'

  #vision
    .row
      max-width: 100%
    .content
      background-color: $light-gray
      padding: 5rem 4rem 3.5rem
    .photo
      margin-left: -5rem
      img
        box-shadow: 0 0 .3rem rgba(0, 0, 0, 0.3)
        border: .06rem solid rgba(179, 179, 179, 0.73)
</style>
