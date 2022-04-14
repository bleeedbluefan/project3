<template>
<div>
  <CountryList :products="products" />
</div>
</template>

<script>
import CountryList from "../components/CountryList.vue"
export default {
  name: 'HomeView',
  components: {
    CountryList
  },
  data() {
    return {
    }
  },
  computed: {
    products() {
      return this.$root.$data.products;
    }
  },
}
</script>
