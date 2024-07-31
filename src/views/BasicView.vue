<template>
  <p>value값 연결 ----------</p>
  <div class="basic">
    <h3>넘버다다다다,{{ title }}</h3>
    <h3>{{ title }}는 수원장안구에 있다</h3>
    <h3>{{ message }}</h3>
    <p v-html="message"></p>
  </div>

  <div>
    <input type="text" v-model="nickname" />
  </div>
  <div>
    <input type="number" v-model="age" />
  </div>
  <div>
    <textarea v-model="message" cols="30" rows="10"></textarea>
  </div>
  <div>
    <select name="city" v-model="city">
      <option value="01">서울</option>
      <option value="02">부산</option>
      <option value="03">대구</option>
      <option value="04">수원</option>
    </select>
  </div>
  <div>
    <label><input type="checkbox" v-model="cbox" /></label>
    <label><input type="checkbox" v-model="cbox2" /></label>
    <label for=""><input type="checkbox" v-model="cbox" />{{ cbox }}</label>
  </div>
  <div>
    <p>좋아하는음식은??</p>
    <label for=""
      ><input type="checkbox" v-model="goodfood" value="마라탕" />마라탕</label
    >
    <label for=""
      ><input type="checkbox" v-model="goodfood" value="민초" />민초</label
    >
    <label for=""
      ><input type="checkbox" v-model="goodfood" value="홍어삼" />홍어삼</label
    >
    <p>당신이 좋아하는 음식은 {{ goodfood }}입니다</p>
    <br />

    <p>싫어하는 음식은?</p>
    <label for=""
      ><input type="checkbox" v-model="badfood" value="마라탕" />마라탕</label
    >
    <label for=""
      ><input type="checkbox" v-model="badfood" value="민초" />민초</label
    >
    <label for=""
      ><input type="checkbox" v-model="badfood" value="홍어삼" />홍어삼</label
    >
    <p>당신이 싫어하는 음식은 {{ badfood }}입니다</p>
  </div>

  <div>
    <p>성별은</p>
    <label for=""
      ><input type="radio" value="남자" v-model="gender" />남자</label
    >
    <label for=""
      ><input type="radio" value="여자" v-model="gender" />여자</label
    >
    <label for=""
      ><input type="radio" value="무성" v-model="gender" />무성</label
    >
    <p>당신의 성별은 {{ gender }}입니다</p>
  </div>

  <h3>--------속성연결--------</h3>
  <div>
    <img v-bind:src="imgSrc" alt="" v-bind:title="tooltip" />
  </div>
  <div>
    <button v-bind:disabled="show1">눌러줘봐</button>
    <button v-bind:disabled="show2">눌러줘봐</button>
  </div>

  <div>
    <button v-bind:style="btn1" :disabled="show1">눌러줘봐</button>
    <button v-bind:style="btn2" :disabled="show2">눌러줘봐</button>
  </div>

  <h3>-------------제어문------------</h3>
  <div>
    <table style="border: 1px solid gray">
      <thead>
        <tr>
          <th style="border: 1px solid gray">제품명</th>
          <th style="border: 1px solid gray">가격</th>
          <th style="border: 1px solid gray">카테고리</th>
          <th style="border: 1px solid gray">배송료</th>
        </tr>
      </thead>
      <tbody>
        <tr v-bind:key="index" v-for="(item, index) in products">
          <td>{{ item.name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.category }}</td>
          <td>{{ item.delivery }}</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div>
    <p v-if="true">if참일때</p>
    <p v-if="false">if거짓일떄</p>
    <p v-show="true">show참</p>
    <p v-show="false">show거짓</p>
  </div>

  <h3>---------------------------이벤트(v-on/@)------------------</h3>
  <div>
    <button v-on:click="increaseCounter">클릭(증가)</button>
    <button @:click="decreaseCounter">클릭(감소)</button>
    <p>counter:{{ counter }}</p>
    <button @:click="increaseCounter(), showMsg()">증가후 알림창</button>
    <button @:click="decreaseCounter(), showMsg()">감소후 알림창</button>
    <br />
    <input type="number" v-model="countValue" />
    <button @:click="applyCounter">적용</button>
  </div>

  <div>
    <select v-model="cityValue" @change="changeCity">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="대구">대구</option>
      <option value="수원">수원</option>
    </select>
  </div>

  <br />
  <br />
  <div>
    <input
      type="text"
      v-model="emailValue"
      @input="changeEmail"
      placeholder="이메일을 입력하세요"
    />
    <!-- <p>{{emailValue}}/{{errEmail}}</p> -->
    <p v-if="errEmail">{{ errEmail }}</p>
  </div>

  <div>
    <input
      type="text"
      v-model="pwdValue1"
      @input="changePwd1"
      placeholder="비번입력"
    />
    <input
      type="text"
      v-model="pwdValue2"
      @input="changePwd2"
      placeholder="비번확인"
    />
    <p v-if="errEmail">{{ errPwd }}</p>
  </div>
<!-- 메소드 computed -->
<div>
    <p>{{hello()}}</p>
    <p>{{hello()}}</p>
    <p>{{hello()}}</p>

    <p>{{ hello2 }}</p>
    <p>{{ hello2 }}</p>
    <p>{{ hello2 }}</p>
  </div>
  
  <div>
    성: <input type="text" v-model="lastName" @input="changeLastName"><br>
    이름: <input type="text" v-model="firstName" @input="changeFirstName"><br>
    <p>method:  {{ methodFullName() }}</p>
    <p>method:  {{ methodFullName() }}</p>
    <p>computed: {{ computeFullName }}</p>
    <p>computed: {{ computeFullName }}</p>
    <p>fullName: {{fullName}}</p>
    <p>fullName: {{fullName}}</p>
  </div>

  <!-- watch -->
  <div>
    <h4>user_info : {{userInfo}}</h4>
    <input type="text" v-model="userName" >
    <input type="text" v-model="userAge" >
  </div>
  <br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
  끝
</template>

<script>
export default {
  name: "BasicView",
  components: {},
  data() {
    return {
      title: "안성준",
      message: '좋은 <b><span style="color:red">사람</span></b>이다',
      nickname: "우하하하하",
      age: 31 + 3,
      city: "04",
      cbox: true,
      cbox2: false,
      goodfood: [],
      badfood: [],
      gender: [],
      imgSrc: require("@/test/011.jpg"),
      tooltip: "이미지 툴팁",
      show1: true,
      show2: false,
      btn1: {
        backgroundColor: "blue",
        color: "yellow",
      },
      btn2: {
        backgroundColor: "red",
        color: "yellow",
      },
      products: [
        { name: "마우스1", price: 2501, category: "PC용품1", delivery: 1000 },
        { name: "마우스2", price: 2502, category: "PC용품2", delivery: 2000 },
        { name: "마우스3", price: 2503, category: "PC용품3", delivery: 3000 },
      ],
      counter: 0,
      countValue: 10,

      cityValue: "대구",
      emailValue: "",
      errEmail: "",
      pwdValue1: "",
      pwdValue2: "",
      errPwd: "비번을 입력하세요",
    };
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: { increaseCounter(){
      this.counter = this.counter +1;
    },
    decreaseCounter(){
      this.counter = this.counter -1;
    },
    applyCounter(){
      this.counter = this.countValue;
    },
    showMsg(){
      alert('현재값 = >'+ this.counter );
    },
    changeCity(){
      alert('선택하신 도시 : '+this.cityValue);
    },
    changeEmail(){
      console.log('sss');
      // 이메일 형식 정규 표현식
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      // this.errEmail = this.emailValue;
      if(this.emailValue === '' || emailPattern.test(this.emailValue)){
        this.errEmail='';
        console.log('ok'+this.emailValue);
      } else {
        this.errEmail='이메일 형식에 어긋납니다.';
        console.log('err'+this.emailValue);
      }

    },
    changePwd1(){
      if(this.pwdValue1===''){
        this.errPwd='비번을 입력하세요';
      } else if(this.pwdValue2===''){
        this.errPwd='비번확인을 입력하세요';
      } else if(this.pwdValue1===this.pwdValue2){
        this.errPwd='';
      } else {
        this.errPwd='비번이 일치하지 않습니다.';
      }

    },
    changePwd2(){
      if(this.pwdValue1===''){
        this.errPwd='비번을 입력하세요';
      } else if(this.pwdValue2===''){
        this.errPwd='비번확인을 입력하세요';
      } else if(this.pwdValue1===this.pwdValue2){
        this.errPwd='';
      } else {
        this.errPwd='비번이 일치하지 않습니다.';
      }

    },

  }
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 100%;
}
td,
th {
  border: 1px solid #ddd;
  text-align: center;
  padding: 8px;
}
th {
  text-align: center;
  font-weight: 600;
}
</style>
