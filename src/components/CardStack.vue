<template>
  <div class="card-stack">
      <Card v-for="item in walletCards" :key="item.id" :cardItem="item" @click.native="displayActiveCard(item.id)"/>
  </div>
</template>

<script>
import Card from '../components/Card.vue'
export default {
  name: "CardStack",
  
  props: {
  walletCards: Array
  },
    
  components: {
  Card
  },
  
  methods: {
  displayActiveCard(cardID) {
  let activeCard = this.walletCards.find((card) => card.id == cardID)
  this.$emit('activeCard', activeCard)
     }
  }
}
</script>

<style scoped>
.card-stack {
  display: grid;
}
</style>