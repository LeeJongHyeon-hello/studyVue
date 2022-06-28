<template>


  <Modal  @modalClose="modalIsOpen= false;" :modalIsOpen="modalIsOpen" :onerooms="onerooms" :roomNum="roomNum"></Modal>


  <div class="menu">
    <a v-for="(item,i) in menu" :key="i">{{item}}</a>
  </div>

  <Discount v-bind="Object"></Discount>
  <Card @modalIsOpen="modalIsOpen= $event; roomNum=$event"  v-for="(item,i) in onerooms" :key="i" :onerooms="onerooms[i]"/>
  



</template>

<script>
import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './components/Modal.vue';
import Card from './components/Card.vue'


export default {
  name: 'App',
  data(){
    return {
      Object : { name : 'kim', age : '20'},
      roomNum : 0,
      modalIsOpen : false,
      onerooms : data,
      menu : ['Home', 'Shop', 'About'],

    }
  },
  methods :{
    increase(i){
      this.onerooms[i].reportNum ++;
    }
  },

  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a{
  color:white;
  padding: 10px;
}

.img{
  width: 100%;
  margin-top: 40px;
}

body{
  margin: 0;
}

div{
  box-sizing: border-box;
}

.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px; padding: 20px;
}

</style>
