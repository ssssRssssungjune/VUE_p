<template>
  <div class="test">
    <input type="text" value="으아으아으아아아아"><br>
    <input type="text" v-model="nick"/><br>
    <input type="number" v-model="age"><br>
    <textarea name="" id="" cols="30" rows="3">동해물</textarea><br>
    <textarea name="" id="" v-model="message" cols="30" rows="3"></textarea><br>
    <select name="" id="" >
      <option value="01">몰라</option>
      <option value="02">서울</option>
      <option value="03">대구</option>
      <option value="04" selected>부산</option>
    </select>
    <br>
    <select v-model="city" name="" id="" >
      <option value="01">몰라</option>
      <option value="02">서울</option>
      <option value="03">대구</option>
      <option value="04">부산</option>
    </select>
    
  </div>
</template>

<script>
export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      nick:'으흐루꾸끄루르으',
      age:30,
      message:'하느님이 보우ㅏ사',
      city:'03',
      
    };
  },
  setup() {
    
  },
  created() {
    
  },
  mounted() {
    
  },
  unmounted() {
    
  },
  methods: {
    
  }
};
</script>

<style scoped>

</style>