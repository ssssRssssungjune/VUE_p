<template>
  <div class="test">
    <table>
      <thead>
        <th>제품명</th>
        <th>가격</th>
        <th>폼목</th>
        <th>배송료</th>
      </thead>
      <tbody>
        <tr v-for="(item, index) in goods" :key="index">
          <td>{{ item.name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.category }}</td>
          <td>{{ item.delivery }}</td>
        </tr>
      </tbody>
    </table>
    <!-- v-if v-else-if v-else-->
    <p v-if="true">홀랑이</p>
    <p v-if="false">사냥자</p>

    <div>
      <label>국어 <input type="number" v-model="kor" /></label><br />
      <label>영어 <input type="number" v-model="eng" /></label><br />
      <label>수학 <input type="number" v-model="math" /></label><br />
      <p v-if="avg >= 90">A학점{{ avg }}</p>
      <p v-else-if="avg >= 80">B학점{{ avg }}</p>
      <p v-else-if="avg >= 70">C학점{{ avg }}</p>
      <p v-else-if="avg >= 60">D학점{{ avg }}</p>
      <p v-else>F학점</p>
      <p>총점: {{ kor + eng + math }}</p>
      <p>평균: {{ avg }}</p>
    </div>
  </div>

  <div>
    <button @click="showScore">계산</button>
  </div>
<br><br><br><br><br><br>

<div>
    <label>
      <input v-model.number="dan" type="text" placeholder="단 입력" />단
    </label>
    <button @click="calculate">계산</button>
    <ul v-if="results.length">
      <li v-for="(result, index) in results" :key="index">{{ result }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TestView",
  components: {},
  data() {
    return {
      goods: [
        { name: "마우스", price: 10000, category: "PC용품", delivery: 2500 },
        { name: "키보드", price: 30000, category: "PC용품", delivery: 2500 },
        {
          name: "모니터",
          price: 100000,
          category: "PC용품",
          delivery: "무료배송",
        },
      ],
      kor: 0,
      eng: 0,
      math: 0,
      avg: 0,
      
      dan: 0,
      results: [],
    };
  },

  methods: {    
    showScore() {
      this.avg = (this.kor + this.eng + this.math) / 3;
    },


    calculate() {
      if (this.dan < 2 || this.dan > 99) {
        alert('2부터 9까지의 숫자를 입력해주세요.');
        return;
      }
      this.results = [];
      for (let i = 1; i <= 9; i++) {
        const result = `${this.dan} * ${i} = ${this.dan * i}`;
        this.results.push(result);
      }

    
  }
  }}
</script>

<style scoped>
table {
  width: 70%;
  border-collapse: collapse;
}

td,
th {
  border: 1px solid #ddd;
}
</style>