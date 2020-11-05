<template>
  <div id="sidebar">
    <nuxt-link :to="localePath('/')">
      <h1 class="title">
        Muto Tsujimoto
      </h1>
    </nuxt-link>
    <Navigation />
    <span id="copyright">
      © 2020 Muto Tsujimoto
    </span>
  </div>
</template>

<style scoped>
#sidebar {
  text-align: left;
  padding: 20px;
  height: 100%;
}
.title {
  font-family: 'Roboto Mono', -apple-system, BlinkMacSystemFont, "Helvetica Neue", YuGothic, "ヒラギノ角ゴ ProN W3", Hiragino Kaku Gothic ProN, Arial, "メイリオ", Meiryo, sans-serif;
  font-size: 22px;
  margin: 40px 0 40px 0;
  color: #0f2540;
}
#copyright{
  position: absolute;
  font-size: 12px;
  color: #6f7c8c;
  bottom: 20px;
}
</style>
