<template>
  <div id="cards-grid">
    <Card
      v-for="(card, i) in getCards(cardsNumber)"
      :key="i"
      class="item"
      :show-details="showDetails"
      :thumbnail="card.thumbnail"
      :title="card.title"
      :tags="card.tags"
      :description="card.description"
      :infomations="card.infomations"
    />
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
type Infomation = {
  title: string;
  data: string;
};
type Card = {
  thumbnail: string;
  title: string;
  tags: string[];
  description: string;
  infomations: Infomation[];
};
export default Vue.extend({
  props: {
    cards: {
      type: Array as PropType<Card[]>,
      required: true
    },
    showDetails: {
      type: Boolean,
      default: true,
      required: false
    },
    cardsNumber: {
      type: Number,
      default: -1,
      required: false
    }
  },
  methods: {
    getCards (cardsNumber: number): Card[] {
      if (cardsNumber === -1) {
        return this.cards
      }
      const cards: Card[] = []
      for (let i = 0; i < cardsNumber; i++) {
        cards.push(this.cards[i])
      }
      return cards
    }
  }
})
</script>

<style scoped>
#cards-grid {
  display: grid;
  grid-gap: 20px;
  grid-template-columns: repeat(auto-fill, minmax(0, 420px));
  justify-content: flex-start;
  align-items: flex-start;
}
</style>
