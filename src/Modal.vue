<template>
<div class="black-bg" v-if="modalState == true" @click="$emit('closeModal')">
    <div class="white-bg">
    <img :src="product.image" alt="room-img">
    <h4>{{product.title}}</h4>
    <p>{{product.content}}</p>
    <p>{{product.price}}</p>
    </div>
</div>
</template>

<script>
export default {
    name : 'Modal',
    props : {
        product : Object,
        modalState : Boolean,
    },
}
</script>

<style>

</style>