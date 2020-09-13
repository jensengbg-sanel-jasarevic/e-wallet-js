<template>
 <div class="card-object" :class="cardClass">
    <section class="top">
      <img src="@/assets/chip-light.svg" alt="chiplight" />
      <img v-if="walletCards.vendor" :src="require('@/assets/vendor-' + cardClass + '.svg')" :alt="cardClass"
      />
    </section>

    <section class="cardnumber" v-if="walletCards.cardnumber">
    </section>
    
    <section class="bottom">
      <aside class="cardholder-name">
        <p>CARDHOLDER NAME:</p>
        <p>{{walletCards.cardholder}}</p>
      </aside>
      <aside class="valid-thru">
        <span>VALID THRU:</span>
        <p>{{walletCards.month}}/{{walletCards.year}}</p>
      </aside>
    </section>

  </div>
</template>

<script>
export default {
    name: "Card",

    props: {
    walletCards: Object
    },
    
    computed: {
        cardClass() {
            let className = '';

            if(this.walletCards.vendor == 'bitcoin') {
                className = 'bitcoin'
            }
            if(this.walletCards.vendor == 'blockchain') {
                className = 'blockchain'
            }
            if(this.walletCards.vendor == 'evil') {
                className = 'evil'
            }
            if(this.walletCards.vendor == 'ninja') {
                className = 'ninja'
        }
        return className
        }
    }
 };
</script>

<style scoped>
.card-object{
    background-color:#D0D0D0;
}

.bitcoin {
    background-color: #FFAE34;

}
.blockchain {
    background-color: #8B58F9;

}
.evil {
    background-color: #F33355;
}

.ninja {
    background-color: #222222;
}
</style>