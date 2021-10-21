<template>
  <div @click="모달창상태 = false" class="black-bg" v-if="모달창상태 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>
  <h1>원룸샵</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu" href="#">{{menu}}</a>
  </div>
  <div>
    <img class="room-img" src="./assets/room0.jpg" alt="room0">
    <h4 @click="모달창상태 = true">{{products[0]}}</h4>
    <p>50 만원</p>
    <button @click="신고수[0]++">허위매물신고</button>
    <span>신고수 : {{신고수[0]}}</span>
  </div>
  <div>
    <img class="room-img" src="./assets/room1.jpg" alt="room1">
    <h4>{{products[1]}}</h4>
    <p>60 만원</p>
    <button @click="신고수[1]++">허위매물신고</button>
    <span>신고수 : {{신고수[1]}}</span>
  </div>
  <div>
    <img class="room-img" src="./assets/room2.jpg" alt="room2">
    <h4>{{products[2]}}</h4>
    <p>70 만원</p>
    <button @click="신고수[2]++">허위매물신고</button>
    <span>신고수 : {{신고수[2]}}</span>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      모달창상태 : false,
      신고수 : [0,0,0],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      menus : ['Home', 'Products', 'About']
    }
  },
  components: {
  },
  methods:{
    increase(){
      this.신고수++;
    }
  }
}
</script>

<style>
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
  color : white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}


</style>
