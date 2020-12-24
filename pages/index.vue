<template>
  <div>
    <Hello />
    <Index text="Latest works" />
    <CardsGrid :cards="cards" :cards-number="3" :show-details="true" />
    <MoreButton
      title="goto works"
      :path="localePath('/works')"
      class="more-button"
    />
  </div>
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
      title: 'hello'
    }
  }
})
</script>

<style scoped>
.more-button {
  margin-top: 14px;
}
</style>
