<!-- 'view' for the BROWSE PAGE: -->

<template>
    <div>
        <div class="pure-menu pure-menu-horizontal">
        </div>
        <CartList :products="products" />
    </div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
    name: 'CartView',
    components: {
        CartList
    },
    data() {
        return {
            country: '',
        }
    },
    computed: {
        products() {
            return this.$root.$data.products;
        }
    },
    methods: {
        select(country) {
            this.country = country;
        }
    }
}
</script>