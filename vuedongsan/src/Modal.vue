<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" class="room-img">
      <h4>{{원룸들[누른거].title}}</h4>
      <p>{{원룸들[누른거].content}}</p>
      <p>{{원룸들[누른거].price}}원</p>
      <!-- <button @click="close()">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
    name : 'modalComponent',
    props : {
        원룸들 : Array,
        누른거 : Number,
        모달창열렸니:Boolean
    }
}
</script>

<style>

</style>