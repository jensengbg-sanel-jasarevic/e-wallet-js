<template>
  <div id="app">
    <router-view :walletCards="walletCards" @cardInfo="cardToWallet"/>
  </div>
</template>

<script>
export default {
    name: "App",
    
    data () {
    return {
    walletCards: []
     }
    },
   
    methods: {
    cardToWallet(cardObj) {
    this.walletCards.push(cardObj);
    }
  
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #FFFFFF;;
}
</style>