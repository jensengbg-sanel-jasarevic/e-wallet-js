<template>
    <section class="card-form">

    <label for="cardnumber">CARD NUMBER:</label>
    <input name="number" type="text" v-model="formObj.cardnumber" maxlength="16"/>
    
    <label for="cardholder">CARDHOLDER NAME:</label>
    <input type="text" name="cardholder" v-model="formObj.cardholder"/>

    <label for="monthyear">VALID THRU
    <select id="month" name="month" v-model="formObj.month">
      <option value="01">01</option>
      <option value="02">02</option>
      <option value="03">03</option>
      <option value="04">04</option>
      <option value="05">05</option>
      <option value="06">06</option>
      <option value="07">07</option>
      <option value="08">08</option>
      <option value="09">09</option>
      <option value="10">10</option>
      <option value="11">11</option>
      <option value="12">12</option>
    </select>
    <select id="year" name="year" v-model="formObj.year">
      <option value="20">20</option>
      <option value="21">21</option>
      <option value="22">22</option>
      <option value="23">23</option>
      <option value="24">24</option>
    </select>
    </label>

    <label for="ccv" >CCV</label>
    <input type="text" name="ccv" v-model="formObj.ccv" maxlength="3"/>

    <label for="vendor">VENDOR</label>
    <select id="vendor" name="vendor" v-model="formObj.vendor">
      <option value="bitcoin">BITCOIN</option>
      <option value="blockchain">BLOCKCHAIN</option>
      <option value="evil">EVIL</option>
      <option value="ninja">NINJA</option>
    </select>
    
    <button @click="formValues">ADD CARD</button>
  
  </section>
</template>

<script>
export default {
    name: "CardForm",
    
    data () {
    return {
     formObj: {
          id: "", cardnumber: "", cardholder: "", year: "", month: "", ccv: "", vendor: ""
        }
      }
    },
     
    methods: {
    formValues() {
      this.$emit('cardInfo', { cardInfo: this.formObj });
      }
    }
};
</script>

<style >

</style>