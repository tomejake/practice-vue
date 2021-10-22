<template>
  <Modal :product = "products[pressNumber]" :modalState = "modalState" @closeModal="modalState=false;"/>
  <h1>REAL ESTATE</h1>
  <Discount />
  <div class="menu">
    <a v-for="menu in menus" :key="menu" href="#">{{menu}}</a>
  </div>
  <Card :product="products[i]" v-for="(product, i) in products" :key="i" @openModal="modalState = true; pressNumber = $event"/>
</template>

<script>
import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  data(){
    return{
      pressNumber : 0,
      products : data,
      modalState : false,
      menus : ['Home', 'Products', 'About'],
    }
  },
  components: {
    Discount,
    Modal,
    Card,
  },
  methods:{
  }
}
</script>

<style>

.discount{
  background: #eee;
  margin: 10px;
  padding: 10px;
  border-radius: 5px;
}

body {
  margin: 0;
  padding: 0;
}

div {
  box-sizing: border-box;
}

.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 15px;
}

.menu a {
  text-decoration: none;
  color : white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}


</style>
