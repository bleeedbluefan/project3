<template>
    <div>
        <p>Please Enter If You Know the State Capital</p>
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
            return this.$root.$data.fullCart;
        }
    }

}
</script>
