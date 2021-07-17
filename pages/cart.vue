<template>
    <div>
        <v-img
        :src="require('@/assets/Arena-fg.png')"
        :lazy-src="require('@/assets/Arena-fg.png')"
    
        >
        <v-container v-if="cart.length != 0">
        <Anounce color="#11131B" :highlight="cart.length" icon="mdi-cart-minus"/>
        <Cart/>
        </v-container>
        <v-container v-else style="margin-top:200px">
            <div class="text-center"
            >
                <h1>Cart is Empty</h1>
            </div>
        </v-container>
        </v-img>
    </div>
</template>

<script>
    import { mapState } from 'vuex'
    import Cart from '~/components/usercart.vue'
    import Anounce from '~/components/alert.vue'
    export default {
        middleware: 'loggedin',
        components:{
            Cart,
            Anounce
        },
        computed:{
            ...mapState(['cart'])
        }
    }
</script>

<style lang="scss" scoped>

</style>