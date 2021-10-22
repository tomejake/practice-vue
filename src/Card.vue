<template>
  <div>
    <img class="room-img" :src="product.image" alt="room-img">
    <h4>{{product.title}}</h4>
    <p>{{product.price}}</p>
  </div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        product : Object,
    },
}
</script>

<style>

</style>