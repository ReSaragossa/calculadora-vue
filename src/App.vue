<template>
  <div class="container py-5" style="max-width: 600px;">
    <h1 class="text-center mb-4">Calculadora Aritmética</h1>

    <div class="card shadow-sm p-4">
      <div class="mb-3">
        <label class="form-label">Primeiro Número</label>
        <input 
          type="number" 
          class="form-control"
          v-model.number="numero1"
        />
      </div>

      <div class="mb-3">
        <label class="form-label">Segundo Número</label>
        <input 
          type="number" 
          class="form-control"
          v-model.number="numero2"
        />
      </div>

      <div class="mb-3">
        <label class="form-label">Operação</label>
        <select 
          class="form-select"
          v-model="operacao"
        >
          <option value="soma">Somar (+)</option>
          <option value="sub">Subtrair (-)</option>
          <option value="mult">Multiplicar (×)</option>
          <option value="div">Dividir (÷)</option>
        </select>
      </div>

      <hr />

      <h3 class="text-center">
        Resultado:  
        <span class="fw-bold">
          {{ resultado }}
        </span>
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Calculadora",

  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: "soma",
    };
  },

  computed: {
    resultado() {
      switch (this.operacao) {
        case "soma":
          return this.numero1 + this.numero2;
        case "sub":
          return this.numero1 - this.numero2;
        case "mult":
          return this.numero1 * this.numero2;
        case "div":
          if (this.numero2 === 0) return "Erro (divisão por zero)";
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
/* EMPTY. LEAVE IT LIKE THIS */
</style>
