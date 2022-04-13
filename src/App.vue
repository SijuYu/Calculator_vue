<template>
  <div class="vuecal">
    <p id="title">brief-calculator</p>
    <div class="input-box">
      first num <input type="number" v-model.number="firstNumb" />
    </div>
    <!--v-model : 폼 입력 바인딩, input과 textarea element에 양방향 데이터 바인딩 생성 가능-->
    <div class="input-box">
      second num <input type="number" v-model.number="secondNumb" />
    </div>

    <div class="btn-box">
      <button @click="operatorPlus">plus</button> &nbsp;
      <button @click="operatorMinus">minus</button> &nbsp;
      <button @click="operatorTimes">times</button> &nbsp;
      <button @click="operatorDiv">division</button> &nbsp;
    </div>

    <div class="result-box">
      <button @click="getresult">결과 값</button>
      <span class="result-box"> &nbsp; {{ result }} </span>
    </div>

    <div class="clear-button"><button @click="clear">AC button</button></div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      result: 0,
      operator: "",
      firstNumb: 0,
      secondNumb: 0,
    };
  },
  methods: {
    operatorPlus() {
      this.operator = "+";
    },
    operatorMinus() {
      this.operator = "-";
    },
    operatorTimes() {
      this.operator = "*";
    },
    operatorDiv() {
      this.operator = "/";
    },
    getresult() {
      if (this.operator == "+") {
        this.result = this.firstNumb + this.secondNumb;
      } else if (this.operator == "-") {
        this.result = this.firstNumb - this.secondNumb;
      } else if (this.operator == "*") {
        this.result = this.firstNumb * this.secondNumb;
      } else {
        this.result = this.firstNumb / this.secondNumb;
      }
    },
    clear() {
      this.operator = "";
      this.firstNumb = 0;
      this.secondNumb = 0;
      this.result = 0;
    },
  },
};
</script>

<style lang="scss">
#title {
  font-size: 32px;
  font-weight: bold;
}

.vuecal {
  width: 540px;
  height: 540px;
  background-color: rgb(255, 255, 255);
  border: 2px solid black;
  margin-left: 640px;
  margin-top: 120px;

  text-align: center;
}

.input-box {
  height: 80px;
  line-height: 80px;

  font-size: 20px;
}

.btn-box {
  margin-top: 20px;
}

.result-box {
  margin-top: 20px;
  font-size: 20px;
}

.result-box > button {
  margin-top: 20px;
  font-size: 16px;
}

.clear-button {
  margin-top: 20px;
}
</style>
