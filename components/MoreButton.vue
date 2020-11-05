<template>
  <div class="button-content">
    <nuxt-link :to="path">
      <span>{{ title }}</span>
    </nuxt-link>
    <div class="arrow">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 28.47 4.53">
        <line class="cls-1" y1="4.03" x2="28.35" y2="4.03" />
        <line class="cls-1" x1="14.17" y1="0.49" x2="28.35" y2="4.03" />
      </svg>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
export default Vue.extend({
  props: {
    title: {
      type: String,
      required: true
    },
    path: {
      type: String,
      required: true
    }
  }
})
</script>

<style>
.button-content {
  font-family: 'Roboto Mono', -apple-system, BlinkMacSystemFont, "Helvetica Neue", YuGothic, "ヒラギノ角ゴ ProN W3", Hiragino Kaku Gothic ProN, Arial, "メイリオ", Meiryo, sans-serif;
  font-size: 12px;
  display: flex;
}
.arrow {
  margin-left: 5px;
  width: 25px;
}
a {
  text-decoration: none;
  color: #0f2540;
}
.cls-1 {
  fill: none;
  stroke: #231815;
  stroke-miterlimit: 10;
}
</style>
