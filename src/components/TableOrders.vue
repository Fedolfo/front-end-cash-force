<template>
  <div class="container-conteudo">
    <div class="container-text-proposta">
      <h3>
        <img
          src="../assets/proposta-table.svg"
          alt="proposta"
          class="logo-proposta"
        />
        Notas fiscais
      </h3>
      <p>Visualize as notas fiscais que você tem.</p>
    </div>
    <div class="container-body-table">
      <div class="container-board">
        <div class="header-board">
          <table class="container-table">
            <thead class="container-table-head">
              <tr class="container-table-row">
                <th>nota fiscal</th>
                <th>sacado</th>
                <th>cedente</th>
                <th>emissão</th>
                <th>valor</th>
                <th>status</th>
              </tr>
            </thead>
            <tbody>
              <tr class="container-table-row">
                <td>1</td>
                <td>01/01/2020</td>
                <td>R$ 1.000,00</td>
                <td>R$ 1.000,00</td>
                <td>R$ 1.000,00</td>
                <td>R$ 1.000,00</td>
                <td><button type="button">Dados do cedente</button></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TableOrders',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.container-conteudo {
  display: flex;
  flex-direction: column;
  align-items: center;
  align-items: flex-start;
  margin-left: 400px;
}

.container-conteudo .container-text-proposta h3 {
  display: flex;
  align-items: center;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 28px;
  color: #021b51;
}

.container-conteudo .container-text-proposta p {
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;

  color: #727d94;
}

.logo-proposta {
  margin-right: 6px;
}

.container-body-table {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.container-board {
  display: flex;
  flex-direction: column;
  border-radius: 5px;
}

.header-board {
  width: 100%;
  height: 50px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.container-table {
  border-spacing: 0 0.8rem;
}

.container-table-row {
  height: 40px;
  font-weight: 600;
  font-size: 1rem;
}

.container-table-row th {
  text-align: center;
  color: #a1a8b8;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 12px;
  line-height: 16px;
  text-transform: uppercase;

  padding: 0 0.3rem;
}

.container-table-row td {
  text-align: left;
  padding: 0 3rem;
  color: #4d5566;
  border-bottom: solid 1px #e6e6e6;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 18px;
}

.container-table-row td button {
  padding: 8px 29px;
  width: 165px;
  height: 32px;
  border: 1px solid #cad3ff;
  border-radius: 24px;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 12px;
  line-height: 16px;
}
</style>
