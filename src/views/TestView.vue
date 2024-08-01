<template>
  <div class="test">
    <!-- 속성연결 -->
     <img src="../test/011.jpg" alt="" title="오!! 하는 유니콘"> <br>
     <button :disabled="btn_01" :style="color_red">못~누루지롱</button> <br>
     <img  v-bind:src="imgSrc" v-bind:title="imgTitle"> <br>
  </div>
  <div>
    
    <button :disabled="btn_02" :style="color_blue">눌러봐</button>
  </div>
</template>

<script>
export default {
  name: 'TestView',
  components: {
    
  },
  data() {
    return {
      imgSrc: require("@/test/011.jpg"),
      imgTitle: '오!하는 유니콘',
      btn_01: true,
      btn_02: false,
      color_blue:{color:"blue",fontSize:"24px"},
      color_red:{color:"red",fontSize:"24px"},
    };
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