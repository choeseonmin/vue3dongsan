<template>
  <div class="black-bg" v-if="모달창열림 == true">
      <div class="white-bg">
        <img :src="원룸들[누른거].image" style="width: 100%">
        <br><br><br><br><h4>{{원룸들[누른거].title}}</h4>
        <p>{{원룸들[누른거].content}}</p>
        <input v-model="month">
        <p> {{ month }}개월 선택 : {{원룸들[누른거].price * month}}원</p> 
        <button @click="$emit('closeModal')">닫기</button>
        <!-- $emit은 애미(부모)컴포넌트 에게 데이터를 보낸다고 생각 -->
      </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return { 
        month : 1,
    }
  },

  watch: {
    month(a) { 
      if (a >= 13){
        alert('13개월 이상 입력하지 마십시오')
      }
      else if (isNaN(a) == true){
        alert('숫자만 입력이 가능합니다.')
        this.month = 1;
      }
      else {
        this.month = a;
      }
    },
  },
  props: {
    원룸들 : Array,
    누른거 : Number,
    모달창열림 : Boolean
  }

}
</script>

<style>

</style>