<template>
  <div>
    <div id="button" :class="{ opened : isOpened }" @click="toggleSidebar()">
      <span class="line l1" />
      <span class="line l2" />
      <span class="line l3" />
    </div>
    <Sidebar id="sidebar" :class="{ opened : isOpened }" />
    <div id="main">
      <Nuxt />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data () {
    return {
      isOpened: false
    }
  },
  watch: {
    $route (to, from) : void {
      if (to.path !== from.path && this.isOpened) {
        this.toggleSidebar()
      }
    }
  },
  methods: {
    toggleSidebar (): void {
      this.isOpened = !this.isOpened
    }
  }
})
</script>

<style>
/* ******************************* */
.page-enter-active {
  transition: all 0.3s ease;
}
.page-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}
.page-enter,
.page-leave-to {
  opacity: 0;
}
.page-enter {
  transform: translateX(-10px);
}
.page-leave-to {
  transform: translateX(10px);
}
/* ******************************* */
body {
  font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", YuGothic, "ヒラギノ角ゴ ProN W3", Hiragino Kaku Gothic ProN, Arial, "メイリオ", Meiryo, sans-serif;
  background: #f0f2f5;
}
#main {
  padding: 60px 18px 60px 300px;
}
#sidebar{
  background: #f0f2f5;
  width: 300px;
  position: fixed;
  left: 0;
  top: 0;
}
@media screen and (max-width: 759px){
  #main {
  padding: 60px 18px 60px 18px;
  }
  #sidebar {
    transition: all 300ms cubic-bezier(1, 0, 0.53, 1);
    left: -100%;
    width: 100%;
  }
  #sidebar.opened{
    z-index: 998;
    left: 0;
  }
  #button {
    transition: all 300ms cubic-bezier(1, 0, 0.53, 1);
    background: #ffffff;
    border: 1px solid #0f2540;
    border-radius: 2px;
    width: 40px;
    height: 40px;
    top: 10px;
    right: 10px;
    cursor: pointer;
    position: fixed;
    z-index: 999;
  }
  .line {
    transition: all 300ms cubic-bezier(1, 0, 0.53, 1);
    width: 22px;
    height: 1px;
    left: 8px;
    background-color: #0f2540;
    position: absolute;
  }
  .l1 {
    top: 13px;
  }
  .l2 {
    top: 19px;
  }
  .l3 {
    top: 25px;
  }
  #button.opened{
    background: none;
    border: none;
  }
  #button.opened .l1{
    top: 19px;
    left: 6px;
    transform: rotate(-45deg);
  }
  #button.opened .l2{
    left: 60%;
    opacity: 0;
  }
  #button.opened .l3{
    top: 19px;
    left: 6px;
    transform: rotate(45deg);
  }
}
/* -------------------------------------- */
*,
*::before,
*::after {
  box-sizing: border-box;
}
ul[class],
ol[class] {
  padding: 0;
}
body,
h1,
h2,
h3,
h4,
p,
ul[class],
ol[class],
figure,
blockquote,
dl,
dd {
  margin: 0;
}
html {
  scroll-behavior: smooth;
}
body {
  min-height: 100vh;
  text-rendering: optimizeSpeed;
  line-height: 1.5;
}
ul[class],
ol[class] {
  list-style: none;
}
a:not([class]) {
  text-decoration-skip-ink: auto;
}
img,
picture {
  max-width: 100%;
  display: block;
}
article > * + * {
  margin-top: 1em;
}
input,
button,
textarea,
select {
  font: inherit;
}
img:not([alt]) {
  filter: blur(10px);
}
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
</style>
