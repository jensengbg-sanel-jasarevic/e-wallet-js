<template>
 <div class="card-object" :class="cardClass">
    <section class="top">
      <img src="@/assets/chip-light.svg" alt="chiplight" />
      <img v-if="cardItem.vendor" :src="require('@/assets/vendor-' + cardClass + '.svg')" :alt="cardClass"/>
    </section>

    <section class="cardnumber">
        <p>{{ cardItem.cardnumber }}</p>
    </section>
    
    <section class="bottom">
      <aside class="cardholder-name">
        <span>CARDHOLDER NAME: </span>
        <p>{{ cardItem.cardholder }}</p>
      </aside>
      <aside class="valid-thru">
        <span>VALID THRU: </span>
        <p>{{ cardItem.month }}/{{ cardItem.year }}</p>
      </aside>
    </section>

  </div>
</template>

<script>
export default {
    name: "Card",

    props: {
    cardItem: Object,
    },
    
    computed: {
    cardClass() {
      let className = '';
        if(this.cardItem.vendor == 'bitcoin') {
                className = 'bitcoin'
            }
        if(this.cardItem.vendor == 'blockchain') {
                className = 'blockchain'
            }
        if(this.cardItem.vendor == 'evil') {
                className = 'evil'
            }
        if(this.cardItem.vendor == 'ninja') {
                className = 'ninja'
            }
        return className;
        }
    }
 };
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=PT+Mono&display=swap');

.card-object{
    background: linear-gradient(248.3deg, rgba(255, 255, 255, 0.24) 0%, rgba(255, 255, 255, 0) 100%), #D0D0D0;
    box-shadow: 0px 0px 16px rgba(0, 0, 0, 0.08);
    border-radius: 8px;
    height: 20rem;
}

.top {
  display: flex;
  justify-content: space-between;
  margin-left: 1rem;
  margin-right: 1rem;
}

.cardnumber {
    font-family: PT Mono;
    font-style: normal;
    font-weight: normal;
    font-size: 29px;
    line-height: 32px;
    letter-spacing: 0.03em;
    color: #000000;
    display: flex;
    justify-content: center;
}

.bottom {
  display: flex;
  justify-content: space-between;
}

.cardholder-name p {
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 20px;
  color: #000000;
  text-align: left;
}

.valid-thru {
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;  
  line-height: 20px;
  color: #000000;
}

span {
  font-family: PT Mono;
  font-style: normal;
  font-weight: normal;
  font-size: 12px;
  line-height: 13px;
  color: rgba(0, 0, 0, 0.8);
}

.bitcoin {
  background: linear-gradient(248.04deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 99.07%), #FFAE34;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  border-radius: 8px;
  
}

.blockchain {
  background: linear-gradient(248.52deg, rgba(0, 0, 0, 0.15) 1.49%, rgba(0, 0, 0, 0) 100%), #8B58F9;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
  border-radius: 8px;
}

.evil {
    background: linear-gradient(248.3deg, rgba(0, 0, 0, 0.16) 0%, rgba(0, 0, 0, 0) 100%), #F33355;
    box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
    color: #fff;
}

.ninja {
   background: linear-gradient(248.3deg, rgba(255, 255, 255, 0.15) 0%, rgba(255, 255, 255, 0) 100%), #222222;
   box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.2);
   border-radius: 8px;
}
</style>