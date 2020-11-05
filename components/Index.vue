<template>
  <div class="index">
    <h3 class="text">
      {{ text }}
    </h3>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    text: {
      type: String,
      required: true
    }
  }
})
</script>

<style scoped>
.index{
  margin-top: 50px;
  margin-bottom: 20px;
}
.text {
  font-family: 'Roboto Mono', -apple-system, BlinkMacSystemFont, "Helvetica Neue", YuGothic, "ヒラギノ角ゴ ProN W3", Hiragino Kaku Gothic ProN, Arial, "メイリオ", Meiryo, sans-serif;
  margin-top: 8px;
  position: relative;
  color: #0f2540;
  font-size: 20px;
  font-weight: 300;
}
.text::before {
  content: "";
  display: block;
  position: absolute;
  top: -8px;
  left: 0;
  width: 80px;
  height: 1px;
  background: #1a1e24;
}
</style>
