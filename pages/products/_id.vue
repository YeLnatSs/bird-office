<template>
  <b-container fluid="xl">
    <b-row>
      <b-col md="7" sm="12">
        <h2 class="product-title">{{ info.title }}</h2>
        <p class="product-price">EUR&nbsp;{{ info.price | numberFormat }}</p>
        <p class="product-description">{{ info.description1 }}</p>
        <p class="product-description">{{ info.description2 }}</p>

        <p class="product-description --detail">{{ info.details }}</p>

        <div class="product-footer">
          <div class="product-quantity">
            <b-button @click.prevent="decrement" class="product-quantity-btn">-</b-button>
            <input class="product-counter" v-model="count">
            <b-button @click.prevent="increment" class="product-quantity-btn">+</b-button>
          </div>
          <b-button @click="stock(count)" class="product-add-to-cart">Add to Cart</b-button>

        </div>
      </b-col>
      <b-col md="5" sm="12">
        <b-img fluid class="product-img" src="http://lorempixel.com/440/831" :alt="info.title"></b-img>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import numeral from 'numeral';
import Subtitle from '~/components/Subtitle.vue'
import products from '~/assets/data/products.json'

export default {
  components: {
    Subtitle,
  },
  filters: {
    numberFormat: function(val) {
      return numeral(val).format("0,0");
    }
  },
  head() {
    return {
      title: this.info.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.info.description1
        }
      ]
    }
  },
  data () {
    return {
      product: products,
      getid: this.$route.params.id,
      info: [],
      count: 1,
      total: ''
    }
  },
  mounted () {
    this.getProduct()
  },
  methods: {
    getProduct: function() {
      let getProduct = this.product;

      for (let i = 0; i < getProduct.length; i++) {
        if ( getProduct[i]['id'] === this.getid ) {
          this.info = getProduct[i]
          return this.info
        }
      }
    },

    increment: function() {
      this.count += 1;
    },

    decrement: function() {
      if (this.count === 0) {
        return
      }
      this.count -= 1
    },

    stock: function(product) {
      this.total = this.info.price * this.count
      localStorage.count = this.count
      localStorage.total = this.total

      window.location.reload(true)
    }
  }
}
</script>

<style lang="scss" scoped>
.container-xl {
  margin-bottom: 129px;
}

.product {
  &-title {
    font: {
      size: 5.2rem;
      weight: 900;
    }
  }

  &-price {
    color: $yellow;
    text-transform: uppercase;
    font: {
      size: 3.4rem;
      family: 'Circular';
    }
    padding-bottom: 1.6rem;
    border-bottom: 13px solid rgba(254, 189, 23, 0.1);
    margin-bottom: 33px;
  }

  &-description {
    font: {
      size: 1.8rem;
      family: CircularStd;
    }
    line-height: 1.78;
    margin-bottom: 30px;

    &.--detail {
      color: $details;
      font-family: CircularBook;
    }
  }

  &-counter {
    width: 15px;
    background: none;
    border: none;
    text-align: center;
    color: $darkgrey;
  }

  &-quantity {
    border-radius: 3px;
    background-color: rgba(229, 229, 229, 0.5);
    color: $darkgrey;
    width: 121px;
    padding: .4em;
    margin-right: 1.9rem;
    font-size: 1.6rem;
    display: flex;
    justify-content: space-between;
    align-items: center;

    &-btn {
      background: $white;
      color: $grey;
      border-radius: 2px;
      border: solid 1px #e5e5e5;
      font-size: 1.6rem;
      width: 36px;
      height: 36px;
    }
  }

  &-add-to-cart {
    border-radius: 3px;
    background-color: $yellow;
    width: 144px;
    color: $white;
    font-size: 1.7rem;
    padding: .8em;
    text-align: center;
    border: solid 1px rgba(0, 0, 0, 0.15);
  }

  &-img {
    opacity: 0.9;
    border-radius: 4px;
    margin-left: auto;
    display: block;

    @media screen and (max-width: 784px) {
      margin: 60px auto 0;
    }
  }

  &-footer {
    display: flex;
    align-items: center;
  }
}
</style>
