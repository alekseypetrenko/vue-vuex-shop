<template>
  <div class="v-main-wrapper">
    <p>{{title}}</p>
    <v-catalog />
    <v-cart 
        v-if="CART.length"
        :cart_data="CART"
    />
  </div>
</template>

<script>
import vCatalog from "./v-catalog";
import vCart from "./v-cart";
import {mapGetters} from "vuex";

export default {
    name: "v-main-wrapper",
    components: {
        vCatalog,
        vCart
    },
    props: {},
    data() {
        return {
            title: "Main wrapper"
        }
    },
    computed: {
        ...mapGetters([
            'CART'
        ])
    },
    methods: {},
    watcher: {}
}
</script>

<style>
    .v-main-wrapper {
        max-width: 900px;
        margin: 0 auto;
    }
</style>