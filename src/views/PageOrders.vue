<template>
  <div>
    <div class="sider-fornecedor">
      <div class="sider-menu">
        <div class="logo-cash-force">
          <img src="../assets/Logo.svg" alt="logo" />
        </div>
        <div class="menu-button">
          <h5 class="menu-name">
            <img src="../assets/proposta.svg" alt="proposta" />
            Notas fiscais
          </h5>
        </div>
      </div>
      <div>
        <TableOrders />
      </div>
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

.sider-fornecedor {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  height: 100vh;
  width: 18em;
}

.menu-button {
  padding-bottom: 26px;
  margin-top: 48px;
  height: 52px;
  display: flex;
  align-items: center;
  box-shadow: inset 3px 0 0.1px 0 #00ad8c;
}

.logo-cash-force {
  margin-top: 55px;
  width: 10em;
  height: 1.875em;
}

.menu-name {
  display: flex;
  align-items: center;
  margin-top: 1.875em;
  margin-left: 1.875em;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 18px;
  color: #00ad8c;
}

.menu-name img {
  margin-right: 7px;
}
</style>
