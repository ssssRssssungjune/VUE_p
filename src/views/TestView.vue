<template>
  <div class="">
    <select name="" id="">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="대구">대구</option>
      <option value="수원">수원</option>
      <option value="광주" selected>광주</option>
    </select>
    <select v-model="city" @change="changeCity">
      <option value="서울">서울</option>
      <option value="부산">부산</option>
      <option value="대전">대전</option>
      <option value="수원">수원</option>
      <option value="광주">광주</option>
    </select>
    <p>{{ message }}</p>
  </div>
  <div>
    <p>
      <label
        >이메일<input
          type="text"
          placeholder="이메일을 입력하세요"
          v-model="emailValue"
          @input="changeEmail" />
          <p v-if="msgEmail">{{ errPwd }}</p>
          </label
      ><span>{{ msgEmail }}</span>
      
    </p>
    <p>
      <label
        >비밀번호<input
          type="text"
          v-model="pwdValue1"
          @input="changePwd1"
          placeholder="비밀번호를 입력하세요"
      /></label>
      <span>{{ errPwd  }}</span>
    </p>
    <p>
      <label
        >비밀번호확인<input
          type="text"
          v-model="pwdValue2"
          @input="changePwd2"
          placeholder="비밀번호확인을 입력하세요"
      /></label>
      
    </p>
  </div>
</template>
<script>
export default {
  name: "TestView",
  data() {
    return {
      city: "서울",
      message: "안녕하세요 반갑습니다.",
      emailValue: "",
      msgEmail: "",
      errPwd: "",
      errEmail: "",
      pwdValue1: "",
      pwdValue2: "",
    };
  },
  methods: {
    changeEmail() {
      // this.emailValue이 이메일 형식에 맞는지 체크
      const emailExp = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; //문자열 + @ + 문자열 + . + 문자열
      if (this.emailValue.length == 0) {
        this.msgEmail = "이메일을 입력하세요";
      } else if (emailExp.test(this.emailValue) == true) {
        this.msgEmail = "정상적인 이메일 주소입니다.";
      } else {
        this.msgEmail = "이메일 주소가 올바르지 않습니다.";
      }
    },

    changePwd1() {
      const pwdRegex = /[@#]/;
      if (this.pwdValue1 === "") {
        this.errPwd = "비밀번호를 입력하세요";
      } else if (pwdRegex.test(this.pwdValue1)) {
        this.errPwd = "비밀번호에 '@' 또는 '#' 문자는 사용할 수 없습니다.";
      } else if (this.pwdValue2 === "") {
        this.errPwd = "비밀번호확인을 입력하세요";
      } else if (this.pwdValue1.length < 8 || this.pwdValue2.length < 8) {
        this.errPwd = "비밀번호는 최소 8자리수 이상입니다.";
      } else if (this.pwdValue1 === this.pwdValue2) {
        this.errPwd = "비밀번호가 유효합니다.";
      } else {
        this.errPwd = "비밀번호가 일치하지 않습니다.";
      }
    },
    changePwd2() {
      this.changePwd1();
    },

    changeCity() {
      switch (this.city) {
        case "서울":
          this.message = "안녕하세요 반갑습니다.";
          break;
        case "부산":
          this.message = "안녕하십니꺼 반갑스니더.";
          break;
        case "대전":
          this.message = "안녕하셔유 반가워유.";
          break;
        case "수원":
          this.message = "안녕하세요 반갑습니다.";
          break;
        case "광주":
          this.message = "안녕하시오 반갑소잉.";
          break;
        default:
          this.message = "안녕하세요 반갑습니다.";
          break;
      }
    },
  },
};
</script>
<style scoped></style>
