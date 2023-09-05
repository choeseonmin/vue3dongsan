<template>

  <div v-if="1==2">
    안녕하세요
  </div>

  <div v-else>
    안녕하세요2
  </div>

  <div class="black-bg" v-if="모달창열림 == true">
      <div class="white-bg">
        <h4>{{ 원룸들[누른거].title }}</h4>
        <p>{{원룸들[누른거].content}}</p>
        <button @click="모달창열림 = false">닫기</button>
      </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <div v-for="(a,i) in 원룸들" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="모달창열림=true; 누른거 = i ">{{a.title}}</h4>
    <p>{{a.price}}원</p>
  </div>

  </template>   
 
<script>  

import data from './assets/oneroom.js';

export default {
  name: 'App',
  data(){ 
    return {
      누른거 : 0,
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

.black-bg .white-bg h4 {
  margin-top: -30px; /* 여기에 원하는 값(픽셀)을 입력하세요 */
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 150px;
}
.white-bg{
  width: 20%; height:12%; background: white;
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