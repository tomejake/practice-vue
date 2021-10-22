<template>
  <div class="black-bg" v-if="modalState == true">
    <div class="white-bg">
      <img :src="products[pressNumber].image" alt="room-img">
      <h4>{{products[pressNumber].title}}</h4>
      <p>{{products[pressNumber].content}}</p>
      <p>{{products[pressNumber].price}}</p>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    props : {
        products : Object,
        pressNumber : Number,
        modalState : Boolean,
    },
}
</script>

<style>

</style>