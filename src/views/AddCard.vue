<template>
  <div class="add-card">
    <CardForm @cardInfo="formValues"/>
  </div>
</template>

<script>
import CardForm from '../components/CardForm.vue'
export default {
    name: "AddCard",
     
    props: {
      walletCards: Array
    },

    components: {
    CardForm
    },

    data () {
      return {
        addedCard: {
          id: "", cardnumber: "", cardholder: "", year: "", month: "", ccv: "", vendor: ""
        }
      }
    }, 

    methods: {
      formValues(values) {
        this.addedCard = values.cardInfo;
        if(this.addedCard.id == "") {
        this.addedCard.id = Math.round(Math.random() * 1000);
        } 
        this.$emit('cardInfo', this.addedCard)
    }
  }
}
</script>

<style >

</style>
