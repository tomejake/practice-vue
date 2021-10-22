<template>
  <!--<div class="start end" :class="{ end : modalState }">-->
  <transition name = "fade" >
    <Modal :product = "products[pressNumber]" :modalState = "modalState" @closeModal="modalState=false;" />
  </transition>
  <h1>REAL ESTATE</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu" href="#">{{menu}}</a>
  </div>
  <Discount v-if="showDiscount == true" :salePer = "salePer" />
  <button @click="priceSort">가격순 정렬</button>
  <button @click="sortBack">정렬 되돌리기</button>
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
      salePer : 30,
      showDiscount : true,
      originalProductsData : [...data],
      pressNumber : 0,
      products : data,
      modalState : false,
      menus : ['Home', 'Products', 'About'],
    }
  },
  mounted(){
    setInterval(()=>{
      if(this.salePer != 0){
        this.salePer--;
      }
    }, 1000);
  },
  components: {
    Discount,
    Modal,
    Card,
  },
  methods:{
    priceSort(){
      this.products.sort(function(a, b){
        return a.price - b.price;
      });
    },
    sortBack(){
      this.products = [...this.originalProductsData];
    },
  }, 
  
}
</script>

<style>
.fade-leave-from {
  opacity: 1;
}

.fade-leave-active {
  transition: all 2s;
}

.fade-leave-to {
  opacity: 0;
}

.fade-enter-from {
  transform: translateY(-1000px);
}

.fade-enter-active {
  transition: all 2s;
}

.fade-enter-to {
  transform: translateY(0px);
}

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
