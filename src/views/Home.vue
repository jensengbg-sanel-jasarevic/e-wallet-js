<template>
  <div class="home-section">
        <Card :walletCards="walletCards"/>
        <CardStack :walletCards="walletCards" />
  </div>
</template>

<script>
import Card from '../components/Card.vue'
import CardStack from '../components/CardStack.vue'

export default {
    name: 'Home',
      
      
    components: {
    Card, 
    CardStack
  },
    props: {
    walletCards: Array
  },
  methods: {
    displayActiveCard() {
    }
  }
}     
</script>

<style>

</style>
