<template>
  <div class="card-stack">
      <Card
      v-for="item in walletCards" :key="item.id" :walletCards="item" 
    />
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
      displayActiveCard() {
      }
  }
}
</script>

<style scoped>
.card-stack {
  display: grid;
}
</style>