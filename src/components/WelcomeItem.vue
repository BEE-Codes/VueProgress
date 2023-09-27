<template>
  <div>
    <input type="number" v-model="num1">
    <input type="number" v-model="num2">
    <select v-model="operator">
      <option>+</option>
      <option>-</option>
      <option>*</option>
      <option>/</option>
    </select>
    <button @click="calculate">Calculate</button>
    <p>{{ result }}</p>
  </div>
</template> 


<script>
  export default{

  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0
    }
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.num1 + this.num2
          break
        case '-':
          this.result = this.num1 - this.num2
          break
        case '*':
          this.result = this.num1 * this.num2
          break
        case '/':
          this.result = this.num1 / this.num2
          break
      }
    }
  }
}
</script>

<style scoped>

</style>