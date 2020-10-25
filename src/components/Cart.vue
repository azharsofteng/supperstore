<template>
    <table class="table table-bordered">
        <thead>
            <tr>
                <th>Name</th>
                <th>Price</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(item, index) in items" :key="index">
                <td>{{ item.title }}</td>
                <td>${{ item.price }}</td>
                <td><button @click="removeItem(index)" class="btn btn-danger btn-sm px-3">X</button></td>
            </tr>
            <tr>
                <th>Total</th>
                <td colspan="2" class="text-center">${{ totalPrice }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>

export default {
    props: ['items'],
    computed:{
        totalPrice(){
            var total = 0
            this.items.forEach(item => {
                total += parseFloat(item.price)
            })
            return total
        }
    },methods:{
        removeItem(index){
            this.$emit('itemRemove', index)
        }
    }
}
</script>

<style>

</style>