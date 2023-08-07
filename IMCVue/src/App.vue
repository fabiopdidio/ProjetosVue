<template>
  <div>
    <h1>Calculadora de IMC</h1>
    <input type="number" placeholder="Altura em metros" v-model="altura" />
    <input type="number" placeholder="Peso em Kg" v-model="peso" />
    <button @click="calcularImc">Calcular</button>
    <h2>{{ resultado }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      altura: 0,
      peso: 0,
      resultado: "",
    };
  },
  methods: {
    calcularImc() {
      // Define aviso em caso do usuário não preencher os campos ou digitar 0
      if (this.peso === 0 || this.altura === 0) {
        alert("Preencha todos os dados");
        return;
      }
      // Fórmula do IMC
      let imc = (this.peso / this.altura ** 2).toFixed(2);
      // Mensagem ao usupario, baseado no resultado do cálculo
      if (imc < 18.5) {
        this.resultado = `IMC ${imc} - Abaixo do peso.`;
      } else if (imc >= 18.5 && imc <= 24.9) {
        this.resultado = `IMC ${imc} - Peso ideal.`;
      } else if (imc >= 25 && imc <= 29.9) {
        this.resultado = `IMC ${imc} - Sobrepeso.`;
      } else if (imc > 30) {
        this.resultado = `IMC ${imc} - Obesidade.`;
      }
    },
  },
};
</script>
<style></style>
