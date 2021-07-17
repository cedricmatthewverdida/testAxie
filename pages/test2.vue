<template>
    <div>

    </div>
</template>

<script>
    import Moralis from 'moralis';
    export default {
        mounted(){
                    const currentUser =  Moralis.User.current();
                    currentUser.set("cart",'')
                    currentUser.save()
        }
    }
</script>

<style lang="scss" scoped>

</style>