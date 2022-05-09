<template>
  <div>
    <div class="sider-fornecedor">
      <div class="logo-cash-force">
        <img src="../assets/Logo.svg" alt="logo" />
      </div>
      <div class="menu-button">
        <h5 class="menu-name">
          <img
            src="../assets/proposta.svg"
            alt="proposta"
            class="logo-proposta"
          />
          Notas fiscais
        </h5>
      </div>
    </div>
    <div>
      <TableOrders />
    </div>
  </div>
</template>

<script>
import TableOrders from '../components/TableOrders.vue';

export default {
  name: 'PageOrders',
  components: {
    TableOrders,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.menu-button {
  border-bottom: #00ad8c solid 1px;
  padding-bottom: 10px;
  width: 100%;
}

.sider-fornecedor {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  width: 288px;
  height: 144px;
}

.logo-cash-force {
  position: absolute;
  width: 160px;
  height: 30px;
  left: 24px;
  top: 25px;
}

.menu-name {
  display: flex;
  align-items: center;
  margin-top: 30px;
  margin-left: 30px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 18px;
  color: #00ad8c;
}

.logo-proposta {
  margin-right: 10px;
  color: #00ad8c;
}
</style>
