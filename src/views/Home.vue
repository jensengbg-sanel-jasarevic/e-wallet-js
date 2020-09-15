<template>
  <div class="home-section">
        <Top :header="header" :activated="activated" />
        <Card :cardItem="selectedCard" />
        <CardStack :walletCards="walletCards" @activeCard="displayActiveCard"/>
        <router-link to="/AddCard"><button class="newcard-button">ADD A NEW CARD</button></router-link>
  </div>
</template>

<script>
import Top from '../components/Top.vue'
import Card from '../components/Card.vue'
import CardStack from '../components/CardStack.vue'
export default {
  name: 'Home',
  
  data() {
  return {
      header: "E-WALLET",
      activated: false,
      selectedCard: {}
    }
  },        

  components: {
  Top,
  Card, 
  CardStack
  },

  props: {
  walletCards: Array
  },
  
  methods: {
  displayActiveCard(activeCard) {
  this.selectedCard = activeCard;
  this.activated = true;
    }
  }
}     
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=PT+Mono&display=swap');

.newcard-button {
  font-family: PT Mono;
  font-style: normal;
  font-weight: bold;
  font-size: 22px;
  line-height: 25px;
  text-align: center;
  color: #000000;
}

</style>
