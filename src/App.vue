<template>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>


<!-- 할인배너를 컴포넌트화 한 것 -->
<Discount/>

<button @click="priceSort">가격 낮은 순</button>
<button @click="priceHigh">가격 높은 순</button>
<button @click="sortABC">가나다순</button>
<button @click="sortBack">되돌리기</button>


<Transition name="fade">
  <!-- Modal.vue에 Props 문법을 이용해 데이터를 전송하는 문법 -->
  <Modal @closeModal="모달창열림 = false" :원룸들="원룸들" :누른거="누른거" :모달창열림="모달창열림" />
</Transition>

  

<Card @openModal="모달창열림 = true; 누른거 = $event" :원룸="원룸들[i]" v-for="(a,i) in 원룸들" :key="a"/>

  
  
</template>   
 
<script>  

// 컴포넌트 데이터들을 import하는 문법
import data from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';



export default {
  name: 'App',
  data(){ 
    return {
      amount : 30,
      showDiscount: true,
      원룸들오리지널 : [...data],
      누른거 : 0,
      원룸들: [...data],
      모달창열림 : false, 
      메뉴들 : ['Home', 'Shop', 'About'],
    }
  },

  // 컴포넌트를 등록하는 것
  components: {
    Discount: Discount,
    Modal: Modal,
    Card: Card,
  },

  methods : {
    sortBack(){
     this.원룸들 = [...this.원룸들오리지널]
    }, 
    priceSort(){
      this.원룸들.sort(function(a,b){
        return a.price - b.price
      })
    },
    priceHigh(){
      this.원룸들.sort(function(a,b){
        return b.price - a.price
      })
    },
    sortABC(){
      this.원룸들.sort(function(a,b){
        return a.title.localeCompare(b.title)
      })
    }
   },
   }
</script>

<style>
.fade-leave-from{ 
  opacity: 1;
}
.fade-leave-active{
  transition: all 1s;
}
.fade-leave-to{
  transform: translateY(-500px);
}


.fade-enter-from {
  transform: translateY(-500px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY( 0px);
}

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
  width: 100%; height: 50%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 150px;
}
.white-bg{
  width:40%; height:40%; background: white;
  border-radius: 10px;
  padding: 60px;
  position: fixed;
  top: 10%; left: 30%;
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
