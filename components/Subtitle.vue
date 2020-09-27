<template>
  <b-container class="mw1034">
    <b-row>
      <b-col>
        <h2 class="subtitle">{{ name }}</h2>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
   props: {
    name: String
  },
}
</script>

<style lang="scss" scoped>
.subtitle {
  margin-bottom: 32px;
  font-family: 'Circular';
  color: $title;
  font-size: 3.2rem;
  font-weight: 900;
}
</style>
