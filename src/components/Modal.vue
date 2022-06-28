<template>
  <div class="black-bg" v-if="modalIsOpen">
    <div class="white-bg">
      <img :src="onerooms[roomNum].image" style="width:100%">
      <h4>{{onerooms[roomNum].title}}</h4>
      <p>{{onerooms[roomNum].content}}</p>
      <input v-model.number="month">
      
      <p>{{month}}개월 선택한 가격: {{onerooms[roomNum].price * month}}원</p>
       <Discount></Discount>
      <button v-on:click="modalClose">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    data(){
      return{
        month : 1,
      }
    },
    watch : {
      
    },
    props :{
      onerooms : Array,
      modalIsOpen : Boolean,
      roomNum : Number,
    },
    methods : {
      modalClose(){
        this.$emit('modalClose',false);
      },
    },
}
</script>

<style>

</style>