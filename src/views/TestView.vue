<template>
    <div>
        <p>Please Type In the State Capitals</p>
        <Test :products="produce" />
    </div>
</template>

<script>
import Test from "../components/Test.vue"
export default {
    name: "TestView",
    components: {
        Test 
    },
    computed: {
        produce() {
            return this.$root.$data.products;
        }
    }

}
</script>
