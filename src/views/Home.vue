<template>
  <div class="home-section">
        <Top :header="header" :activated="activated" />
        <Card :cardItem="selectedCard" />
        <CardStack :walletCards="walletCards" @activeCard="displayActiveCard"/>
        <router-link class="add-link" to="/AddCard">ADD A NEW CARD</router-link>
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

.add-link {
  font-family: PT Mono;
  font-style: normal;
  font-weight: bold;
  font-size: 22px;
  line-height: 25px;
  text-align: center;
  border-radius: 8px;
  color: #000000;
  border: 1px solid #000000;
  box-sizing: border-box;
  padding: 1.5rem;
  margin-top: 2.5rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  text-decoration: none;
}

</style>
