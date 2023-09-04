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
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="모달창열림 = true">{{ products[0] }}</h4>
    <p>50만원</p> 
    <button @click="신고수[0]++">허위매물신고</button> 
    <span> 신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4 @click="모달창열림 = true">{{ products[1] }}</h4>
    <p>60만원</p> 
    <button @click="신고수[1]++">허위매물신고</button> 
    <span> 신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4 @click="모달창열림 = true">{{ products[2] }}</h4>
    <p>70만원</p> 
    <button @click="신고수[2]++">허위매물신고</button>
    <span> 신고수 : {{ 신고수[2] }}</span>
  </div>

  </template>   
 
<script>  


export default {
  name: 'App',
  data(){ 
    return {
      모달창열림 : true,
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