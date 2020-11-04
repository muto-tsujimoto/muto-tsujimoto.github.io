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
  mounted () {
    (console as any).log('ソースコードに興味を持って頂きありがとうございます。\r\nこのWebサイトはNuxt.jsで制作しました。\r\n過去の制作物は/worksに掲載しておりますので、ぜひご覧ください。')
  },
  methods: {
    toggleSidebar (): void {
      this.isOpened = !this.isOpened
    }
  }
})
</script>

<style>
body {
  font-family: 'Noto Sans JP', sans-serif;
  background: #f0f2f5;
}
#main {
  padding: 60px 18px 18px 300px;
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
  padding: 60px 18px 18px 18px;
  }
  #sidebar {
    transition: all 0.2s;
    left: -100%;
    width: 100%;
  }
  #sidebar.opened{
    z-index: 998;
    left: 0;
  }
  #button {
    transition: all 0.3s;
    background: #ffffff;
    border: 1px solid #6f7c8c;
    width: 40px;
    height: 40px;
    top: 10px;
    right: 10px;
    cursor: pointer;
    position: fixed;
    z-index: 999;
  }
  .line {
    transition: all 0.3s;
    width: 26px;
    height: 1px;
    left: 6px;
    background-color: #6f7c8c;
    position: absolute;
  }
  .l1 {
    top: 12px;
  }
  .l2 {
    top: 19px;
  }
  .l3 {
    top: 26px;
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
