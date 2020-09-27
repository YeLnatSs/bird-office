<template>
    <b-card
    no-body
    :img-src="image"
    :img-alt="alt"
    img-top
    class="card-img">

    <b-card-body>
      <router-link class="card-link" :to="`/products/${link}`">${{ price | numberFormat }}&nbsp;&nbsp;{{ description }}</router-link>
    </b-card-body>
  </b-card>
</template>

<script>
import numeral from 'numeral';

export default {
  props: {
    image: String,
    alt: String,
    link: String,
    description: String,
    price: Number,
  },
  filters: {
    numberFormat: function(val) {
      return numeral(val).format('0,0');
    }
  }
}
</script>

<style lang="scss" >
.card {
  margin-bottom: 80px;

  &-link {
    color: $primary-text;
    font: {
      size: 1.5rem;
      weight: 300;
    }
    line-height: 1.2;
  }
}
</style>
