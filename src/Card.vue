<template>
<div>
    <img class="room-img" :src="product.image" alt="room-img">
    <h4 @click="func">{{product.title}}</h4>
    <p>{{product.price}}</p>
</div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        product : Object,
    },
    methods : {
        func(){
            this.$emit('openModal', this.product.id);
        }
    }
}
</script>

<style>

</style>