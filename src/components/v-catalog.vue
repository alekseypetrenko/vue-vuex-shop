<template>
  <div class="v-catalog">
      <v-catalog-item 
        v-for="product in PRODUCTS"
        :key="product.article"
        :product_data="product"
        @addToCart="addToCart"
      />
  </div>
</template>

<script>
import vCatalogItem from "./v-catalog-item";
import {mapActions, mapGetters} from 'vuex';

export default {
    name: "v-catalog",
    components: {
        vCatalogItem
    },
    computed:{
        ...mapGetters([
            'PRODUCTS'
        ])
    },
    methods: {
        ...mapActions([
            'GET_PRODUCTS_GROM_API',
            'ADD_TO_CART'
        ]),
        addToCart(data){
            this.ADD_TO_CART(data)
        },
    },
    mounted() {
        this.GET_PRODUCTS_GROM_API()
    },
    data(){
        return {
        }
    }
}
</script>

<style lang="scss">
    .v-catalog {

            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;

    }
</style>