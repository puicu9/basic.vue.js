<template>

 <!-- S : 모달창  -->
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="close()">닫기</button>
    </div>
  </div>
<!-- E : 모달창  -->

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{a}}</a>
  </div>

  <!-- <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4>{{원룸들[0].title}}</h4>
    <p>{{원룸들[0].price}}원</p>
  </div> -->

<!-- 강의6 숙제 -->
  <div v-for="(a, index) in 원룸들" :key="index">
    <img :src="a.image" class="room-img">
    <h4>{{a.title}}</h4>
    <p>{{a.price}}원</p>
  </div>

</template>

<script>

// 다른 경로로 부터 import하기
import data from './oneroom.js';

export default {
  name: 'App',
  data(){// 데이터 보관함 : 변수 값 할당 등
    return{
      //강의6
      원룸들 : data,

      //강의5 : 모달창
      모달창열렸니: false,

      메뉴들 : ['Home','Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0,0,0],
      tests : [
        {name : '역삼', price : 50, count : 0},
        {name : '천호', price : 60, count : 0},
        {name : '마포', price : 70, count : 0}
      ]
    }
  }
  ,
    // 함수 만드는 공간
  methods: {
    increase(index){
      this.신고수[index] +=1;
    }
    ,increase_test(obj){
      obj.count +=1;
    }
    ,close(){
      this.모달창열렸니= false
    }
  },components: {
  
  }
  
}
</script>


<style>

/* S : 모달창 */
body{
  margin :0
}
div{
  box-sizing :border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position :fixed; padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
/* E : 모달창 */


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img{
  width:100%;
  margin-top: 40px;
}



/* .container {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  align-items: flex-start;
} */

</style>