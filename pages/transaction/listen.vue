<template>
    <div>
        {{transaction_msg}} <br>
        {{transaction}}
    </div>
</template>

<script>
    import Moralis from 'moralis';
    export default {
        data: () => ({
            transaction_msg: 'Nothing Happen Yet',
            transaction:[]
        }),
        methods:{
            async listener(){
                let Transaction = new Moralis.Query("EventSync");
                let subscription = await Transaction.subscribe();

                subscription.on("create", (object) =>{
                    this.transaction_msg = "New Transaction Made!"
                    console.log("Yawa");
                    this.transaction = object
                })
            }
        },
        watch:{
            transaction_msg : function (val){
                return val
            },
            transaction : function (val){
                return val
            }
        },
        mounted(){
            this.listener()
        }
    }
</script>

<style lang="scss" scoped>

</style>