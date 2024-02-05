<template>
  <div id="app" class="container mt-5">
    <h1 class="mb-4">Calculadora Aritmética Vue</h1>
    <div class="row">
      <div class="col-md-4">
        <label for="num1">Número 1:</label>
        <input v-model="num1" type="number" class="form-control" @input="calcularResultado" />
      </div>
      <div class="col-md-4">
        <label for="operator">Operação:</label>
        <select v-model="operacao" class="form-control" @change="calcularResultado">
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col-md-4">
        <label for="num2">Número 2:</label>
        <input v-model="num2" type="number" class="form-control" @input="calcularResultado" />
      </div>
    </div>
    <div class="mt-3">
      <h4>Resultado: {{ resultado }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case '-':
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case '*':
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case '/':
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.resultado = 0;
      }
    },
  },
};
</script>

<style>
/* Adicione estilos adicionais conforme necessário */
</style>
