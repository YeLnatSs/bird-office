<template>
  <div>
      <Subtitle name='Just Booked' />

      <b-container class="mw1034">
        <b-row cols="1" cols-sm="2" cols-md="5">
          <b-col
          v-for="item in allProducts"
          :key="item.id"
          >
            <Cards
            :image="item.image"
            :link="item.id"
            :alt="item.title"
            :price="item.price"
            :description="item.title"
            />
          </b-col>
        </b-row>
      </b-container>

      <Subtitle name='Featured experiences' />

      <b-container class="mw1034">
        <b-row cols="1" cols-sm="2" cols-md="5">
          <b-col
          v-for="item in allProducts"
          :key="item.id">
            <Cards
            :image="item.image"
            :link="item.id"
            :alt="item.title"
            :price="item.price"
            :description="item.title"
            />
          </b-col>
        </b-row>
      </b-container>
  </div>
</template>

<script>
import Subtitle from '~/components/Subtitle.vue'
import Cards from '~/components/Cards.vue'
import products from '~/assets/data/products.json'

export default {
  components: {
    Subtitle,
    Cards
  },
  data () {
    return {
      allProducts: products
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
