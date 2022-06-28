<template>
  <div>
    <img :src="onerooms.image" class="img">
    <h4 v-on:click="modalIsOpen">{{onerooms.title}}</h4>
    <p> {{onerooms.price}}원</p>
    <button v-on:click="increase(i)">허위매물신고</button><span>신고수 : {{onerooms.reportNum}}</span>
  </div>
</template>

<script>
export default {
    name : 'Card',
    props : {
        onerooms : Object,
    },
    methods : {
        modalIsOpen(){
            this.$emit('modalIsOpen',this.onerooms.id);
        },
        
    }
    
}
</script>

<style>

</style>