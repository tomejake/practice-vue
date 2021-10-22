<template>
<div class="black-bg" v-if="modalState == true" >
    <div class="white-bg">
    <img :src="product.image" alt="room-img">
    <h4>{{product.title}}</h4>
    <p>{{product.content}}</p>
    <!--<input type="text" @input="month = $event.target.value">-->
    <input v-model.number="month" type="text">
    <p>{{month}}개월 선택함 : {{product.price * month}}</p>
    <button @click="$emit('closeModal')">닫기</button>
    </div>
</div>
</template>

<script>
export default {
    name : 'Modal',
    data() {
        return{
            month : 3,
        }
    },
    updated(){
        if(this.month < 3 && this.month != ''){
            alert("3개월 이상만 가능");
        }
    },
    watch :{
        month(a){
            if(isNaN(a) == true){
                alert("오류");
            }
        }
    },
    props : {
        product : Object,
        modalState : Boolean,
    },
}
</script>

<style>

</style>