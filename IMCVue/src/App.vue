<template>
  <div>
    <h1>Calculadora de IMC</h1>
    <input type="number" placeholder="Altura em metros" />
    <input type="number" placeholder="Peso em Kg" />
    <button>Calcular</button>
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
  methods: {},
};
</script>
<style></style>
