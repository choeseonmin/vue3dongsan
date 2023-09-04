<template>

  <div class="black-bg" v-if="모달창열림 == true">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>상세페이지 내용</p>
        <button @click="모달창열림 = false">닫기</button>
      </div>
  </div>

  <div class="menu">
    <a v-for="(a,i)  in 메뉴들" :key="i">{{ a }}</a> 
  </div>

  <div>
    <img :src="원룸들[0].image" class="room-img">
    <h4 @click="모달창열림 == true">{{원룸들[0].title}}</h4>
    <p>{{원룸들[0].price}}원</p>
  </div>

  <div>
    <img :src="원룸들[1].image" class="room-img">
    <h4>{{원룸들[1].title}}</h4>
    <p>{{원룸들[1].price}}원</p>
  </div>

  <div>
    <img :src="원룸들[2].image" class="room-img">
    <h4>{{원룸들[2].title}}</h4>
    <p>{{원룸들[2].price}}원</p>
  </div>

  <div>
    <img :src="원룸들[3].image" class="room-img">
    <h4>{{원룸들[3].title}}</h4>
    <p>{{원룸들[3].price}}원</p>
  </div>

  <div>
    <img :src="원룸들[4].image" class="room-img">
    <h4>{{원룸들[4].title}}</h4>
    <p>{{원룸들[4].price}}원</p>
  </div>

  <div>
    <img :src="원룸들[5].image" class="room-img">
    <h4>{{원룸들[5].title}}</h4>
    <p>{{원룸들[5].price}}원</p>
  </div>

  </template>   
 
<script>  

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){ 
    return {
      원룸들: data,
      모달창열림 : false,
      신고수 : [0,0,0],
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['평거동원룸', '가좌동원룸', '칠암동원룸'],
    }
  },

  components: {

  }
}
</script>

<style>

body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 150px;
}
.white-bg{
  width: 20%; height:25%; background: white;
  border-radius: 15px;
  padding: 60px;
  position: fixed;
  top: 10%; left: 40%;
}
.room-img{
  width: 20%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background:  darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

</style>