<template>
  <CardsGrid :cards="cards" />
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data () {
    return {
      cards: (this as any).$t('cards')
    }
  },
  head () {
    return {
      title: 'works'
    }
  }
})
</script>
