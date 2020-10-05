<template>
  <div id="app">
    <router-view :walletCards="walletCards" @cardInfo="cardToWallet" @deleteCard="deleteCard"/>
  </div>
</template>

<script>
export default {
    name: "App",
    
    data () {
    return {
    walletCards: 
    [
      {cardholder: "NAME LASTNAME", cardnumber: "2342343242342342", ccv: "545", id: "978", month: "10", vendor: "bitcoin", year: "21"},
      {cardholder: "NAME LASTNAME", cardnumber: "4534543534534534", ccv: "434", id: "798", month: "11", vendor: "blockchain", year: "22"},
      {cardholder: "NAME LASTNAME", cardnumber: "1212121212121232", ccv: "343", id: "977", month: "12", vendor: "ninja", year: "23"}
    ]
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
  padding: 1rem;
  box-sizing: border-box;
  background-color: #FFFFFF;;
}
</style>