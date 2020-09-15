<template>
<div class="top">
    <h1>{{ header }}</h1>
    <h3 v-if="this.activated">ACTIVE CARD</h3>
</div>
</template>

<script>
export default {
  name: 'Top',

  props: {
  header: String,
  activated: Boolean
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro&display=swap');

h1 {
font-family: Source Sans Pro;
font-style: normal;
font-weight: bold;
font-size: 35px;
line-height: 100%;
text-align: center;
color: #222222;
}

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