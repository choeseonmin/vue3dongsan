<template>
    <div v-for="(a,i) in 원룸들" :key="i">
        <img :src="a.image" class="room-img">
        <h4>{{a.title}}</h4>
        <p>{{a.price}}원</p>
    </div>
  
  
</template>



<script>
export default {
    name: 'Card',
    props: {
        원룸들 : Array,
        누른거 : Number,
        모달창열림 : Boolean,
    }

}

</script>

<style>

</style>