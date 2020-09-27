<template>
  <div class="header-cart">
      <p class="header-product-in-cart">
        <span v-if="totalCount > 0 && totalProduct > 0">
          {{ totalCount }}&nbsp;items ${{ totalProduct | numberFormat }}
        </span>
        <span v-else>
          0
        </span>
      </p>
      <p class="header-text-cart">{{ msg }}</p>
      <a href="#">
        <img
        src="~/assets/img/shopping-cart-icon.png"
        srcset="~/assets/img/shopping-cart-icon@2x.png 2x,
                ~/assets/img/shopping-cart-icon@3x.png 3x"
        class="header-cart-icon">
      </a>
  </div>
</template>

<script>
import numeral from 'numeral';

export default {
  data () {
    return {
      msg: 'shopping cart',
      totalProduct: '',
      totalCount:'',
      get token() {
        return localStorage.getItem('total') || 0;
      },
      set token(value) {
        localStorage.setItem('total', value);
      }
    }
  },
  mounted() {
    this.displayInCart();
  },
  methods: {
    displayInCart: function() {
      this.totalProduct = localStorage.getItem('total')
      this.totalCount = localStorage.getItem('count')
    }
  },
  filters: {
    numberFormat: function (val) {
      return numeral(val).format("0,0");
    }
  },
}
</script>

<style lang="scss" scoped>

</style>
