<template>
  <b-container fluid>
    <b-row class="header">
      <b-col cols="6">
        <a href=/>
          <img
              class="header-logo"
              src="~/assets/img/dewalt-logo.png"
              srcset="~/assets/img/dewalt-logo@2x.png 2x,
                      ~/assets/img/dewalt-logo@3x.png 3x"
              alt="Logo">
        </a>
      </b-col>
      <b-col cols="6">
          <cart-nav/>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import CartNav from '~/components/CartNav.vue'

export default {
  components: {
    CartNav
  }
}
</script>

<style lang="scss" >
.header {
  box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.15);
  height: 80px;
  align-items: center;
  margin-bottom: 80px;

  @media screen and (min-width: 1200px) {
      padding: 0 4.5rem;
    }

  &-logo {
    height: 3.8rem;
    padding-left: 1em;
  }

  &-product-in-cart {
    padding: 2px 6px;
    border: 1px solid $yellow;
    background: $yellow;
    font-size: 1.4rem;
    border-radius: 30px;
    color: $white;
    line-height: 1.2;
    margin-bottom: 0;
  }

  &-text-cart {
    font: {
      size: 1.6rem;
      family: "CircularBook";
    }
    color: $grey;
    margin: {
      left: 1em;
      right: 1em;
      bottom: 0;
    }

    @media screen and (max-width: 785px) {
      display: none;
    }
  }

  &-cart {
    display: flex;
    justify-content: flex-end;
    align-items: center;

    &-icon {
      height: 2em;
    }
  }
}
</style>
