<template>
<router-link class="card-link" :to="`/products/${link}`">
    <b-card
    no-body
    :img-src="image"
    :img-alt="alt"
    img-top
    class="card-img">

    <b-card-body class="card-text">
      ${{ price | numberFormat }}&nbsp;&nbsp;{{ description }}
    </b-card-body>
  </b-card>
  </router-link>
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

@media screen and (min-width: 1200px) {
  &:hover {
    border-color: $yellow;
    .card-link {
      color: $primary-text;
      text-decoration: none;
    }
  }
}

  &-text {
    color: $primary-text;
    font: {
      size: 1.5rem;
      weight: 300;
    }
    line-height: 1.2;
  }
}
</style>
