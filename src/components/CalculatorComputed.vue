<template>
  <section>
    <input placeholder="num1" type="number" v-model.number="num1">
    <select v-model="operand"> 
      <option value="+"> + </option>
      <option value="-"> - </option>
      <option value="*"> * </option>
      <option value="/"> / </option>
    </select>
    <input placeholder="num2" type="number" v-model.number="num2">
    <h2> {{resultadoDaOperacao}} </h2>
  </section>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operand: ""
    };
  },
  computed: {
    resultadoDaOperacao: function() {
      switch(this.operand) {
        case "+":
          return this.num1 + this.num2
        case "-":
          return this.num1 - this.num2
        case "*":
          return this.num1 * this.num2
        case "/":
          return (this.num1 / this.num2).toFixed(2)
      }
      return this.resultadoDaOperacao     
    }
  }
}
</script>

<style scoped>

</style>
