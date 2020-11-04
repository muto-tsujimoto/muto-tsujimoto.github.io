<template>
  <div>
    <ul id="nav">
      <li v-for="(page, i) in pages" :key="i" class="content">
        <nuxt-link class="text" :to="localePath(page.path)">
          {{ page.title }}
        </nuxt-link>
      </li>
    </ul>
    <div id="lang-selector">
      <MoreButton
        v-if="$i18n.locale == 'en'"
        title="日本語"
        :path="switchLocalePath('ja')"
      />
      <MoreButton
        v-if="$i18n.locale == 'ja'"
        title="English"
        :path="switchLocalePath('en')"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data () {
    return {
      pages: [
        { title: 'hello', path: '/' },
        { title: 'profile', path: '/profile' },
        { title: 'works', path: '/works' },
        { title: 'contact', path: '/contact' }
      ]
    }
  }
})
</script>

<style scoped>
ul {
  margin: 0;
  padding: 0;
  text-align: left;
  list-style: none;
}
.content {
  font-family: 'Roboto Mono', monospace;
  padding: 10px 0 10px 0;
}
a.text {
  text-decoration: none;
  color: #0f2540;
  font-size: 16px;
}
#nav .nuxt-link-exact-active {
  background: #0f2540;
}
#nav a.nuxt-link-exact-active {
  color: #f0f2f5;
}
#lang-selector {
  width: 100%;
  margin-top: 30px;
}
#lang-selector a {
  font-size: 12px;
}
#lang-selector a.nuxt-link-exact-active {
  color: #b7bdc5;
}
</style>
