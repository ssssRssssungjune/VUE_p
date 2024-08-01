<template>
  <div class="test">
    <input type="checkbox" id="cdtn_agree" name="cdtn_agree" /><label
      for="cdtn_agree"
      >동의</label> <br>
      
      <label><input type="checkbox" v-model="agree" />동의</label> <br>
      <label><input type="checkbox" v-model="agree2"
        true-value="동의" false-value="비동의" />{{ agree2 }}</label> <br>
      
      <div>
        <p>기본피자에 원하시는 토핑을 추가 하시요</p>
        <label><input type="checkbox" v-model="pizza" value="치즈"/>치즈</label> <br>
        <label><input type="checkbox" v-model="pizza" value="파인애플"/>파인애플</label> <br>
        <label><input type="checkbox" v-model="pizza" value="버섯"/>버섯</label> <br>
        <p>추가로 토핑은 {{ pizza }} 입니다.</p>
      </div>

      <div>
        <p>탕수육 취향은</p>
        <label><input type="radio" v-model="pork" value="부먹">부먹</label> <br>
        <label><input type="radio" v-model="pork" value="찍먹">찍먹</label>
        <p>너의 취향은 <span style="color: red; font-weight: 800;">{{ pork }}</span>이다</p>
      </div>
  </div>
</template>

<script>
export default {
  name: "TestView",
  components: {},
  data() {
    return {
      agree:false,
      agree2:"비동의",
      pizza:[],
      pork:"찍먹",

    };
  },

  mounted() {},
  unmounted() {},
  methods: {},
};
</script>

<style scoped></style>
