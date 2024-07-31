<template>
    <div class="bg"></div>
  <div class="add">
    <h1>회원가입</h1>
    <ul>
        <li class="title">사용자 이름</li>
        <li><input class="checkboxx" type="text" v-model="name"></li>
    </ul>
    <ul>
        <li class="title">이메일</li>
        <li><input class="checkboxx" type="text" v-model="email"></li>
    </ul>
    <ul>
        <li class="title">비밀번호</li>
        <li><input class="checkboxx" type="text" v-model="password"></li>
    </ul>
    <ul>
        <li class="title">비번확인</li>
        <li><input class="checkboxx" type="text" v-model="password"></li>
    </ul>
    <ul>
        <li class="title">성별</li>
        <li><label for=""><input type="radio" value="남자" v-model="gender"> 남자</label>
            &nbsp;
            <label for=""><input type="radio" value="여자" v-model="gender"> 여자</label>
            &nbsp;
            <label for=""><input type="radio" value="무성" v-model="gender"> 무성</label></li>
        

    </ul>
    <ul>
        <li class="title">좋아하는 음식</li>
        <li><select class="checkboxx" name="city">
      <option value="01">한식</option>
      <option value="02" selected>중식</option>
      <option value="03">양식</option>
      <option value="04">몰라</option>
    </select></li>
    </ul>

    <ul>
        <li><input  type="checkbox"> 정보공개동의</li>
       </ul>

       <button class="join">가입하기</button>



  </div>

</template>

<script>
export default {
  name: 'AddView',
  components: {
    
  },
  data() {
    return {
        password:"****",
        email:"voreaasdsa@naver.com",
        name:"홍길동",
      
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

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-align: center;
    
}
h1{
    padding: 10px;
}
li{
    list-style: none;
    font-size: 15px;
    }

ul{
    padding: 10px;
}

.add{
    width: 450px;
    height: 600px;
    background-color: rgb(255, 255, 255);
    border-radius: 10px;
    margin: 50px auto;
    box-shadow: 0 0 15px #7f7f7f;
}

.checkboxx{
    border-radius: 5px;
    border: 1px solid #ccc;
    padding: 5px;
    width: 40%;
    margin-top: 4px;
}

.join{
    padding: 10px;
    width: 110px;
    border-radius: 5px;
    background-color: #4a89ff;
    color: white;
    border: 1px solid #4a89ff;
}
.title{
    font-size: 15px;
    margin-bottom: 3px;
    font-weight: bold;
}
</style>