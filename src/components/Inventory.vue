<template>
    <div class="row">
        <div v-for="(item, index) in items" :key="index" class="card my-2 mx-2" style="width: 16rem;">
            <img :src="item.photo" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ item.title }}</h5>
                <p class="card-text">${{ item.price }}</p>
                <a @click="addToCart(item)" class="btn btn-primary">+ add</a>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['items'],
    methods:{
        addToCart(item){
            this.$emit('newItemAdd', item)
        }
    }
}
</script>

<style>

</style>