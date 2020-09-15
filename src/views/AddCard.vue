<template>
  <div class="add-card">
    <Top :header="header" />
    <h3>NEW CARD</h3>
    <Card :cardItem="cardItem"/>
    <CardForm @cardInfo="listen"/>
  </div>
</template>

<script>
import Top from '../components/Top.vue'
import Card from '../components/Card.vue'
import CardForm from '../components/CardForm.vue'
export default {
    name: "AddCard",
     
    components: {
    Top,
    CardForm,
    Card
    },
    
    props: {
    walletCards: Array
    },
    
    data () {
      return {
        header: "ADD A NEW BANK CARD",
        cardItem: {
          id: "", 
          cardnumber: "XXXX XXXX XXXX XXXX",
          cardholder: "FIRSTNAME LASTNAME",
          month: "MM",
          year: "YY",
          ccv: "",
          vendor: ""
        }
      }
    }, 

    methods: {
      listen(formValues) {
        this.cardItem = formValues.cardInfo;
        if(this.cardItem.id == "") {
        this.cardItem.id = Math.round(Math.random() * 1000);
        } 
        if (formValues.e.type == 'click'){
        this.$emit('cardInfo', this.cardItem)
        }
    }
  }
}
</script>

<style scoped >
@import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro&display=swap');

h3 {
font-family: Source Sans Pro;
font-style: normal;
font-weight: 600;
font-size: 12px;
line-height: 15px;
text-align: center;
color: rgba(34, 34, 34, 0.6);
}
</style>
