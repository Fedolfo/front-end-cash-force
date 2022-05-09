<template>
  <div class="conteudo">
    <h3>
      <img
        src="../assets/proposta-table.svg"
        alt="proposta"
        class="logo-proposta"
      />
      Notas fiscais
    </h3>
  </div>
</template>

<script>
export default {
  name: 'TableOrders',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.conteudo {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-left: 400px;
}

.logo-propostas {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}
</style>
