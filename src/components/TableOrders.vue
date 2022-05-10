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
              <tr
                class="container-table-row"
                v-for="(order, index) in orders"
                :key="index"
              >
                <td>{{ order.orderNfId }}</td>
                <td>{{ order.buyer.name }}</td>
                <td>{{ order.provider.name }}</td>
                <td>{{ formatedData(order.emissionDate) }}</td>
                <td class="value-positive">
                  {{ formatterValue(order.value) }}
                </td>
                <td>
                  {{ receiptStatus(order.orderStatusBuyer) }}
                </td>
                <td>
                  <button type="button">
                    {{ order.provider.tradingName }}
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

const baseURL = 'http://localhost:3001/';

const api = axios.create({ baseURL });

export default {
  name: 'TableOrders',

  data() {
    return {
      orders: [],
    };
  },

  mounted() {
    this.getOrders();
  },

  methods: {
    formatedData(dataUnformated) {
      const data = new Date(dataUnformated);

      const day = data.getDay() + 1;
      const month = data.getMonth() + 1;
      const yaer = data.getFullYear();

      const NUMBERTEN = 10;

      return `${day > NUMBERTEN ? day : `0${day}`}/${
        month > NUMBERTEN ? month : `${month}`
      }/${yaer}`;
    },

    receiptStatus(status) {
      switch (status) {
        case '0':
          return 'Pendente de confirmação';
        case '1':
          return 'Pedido confirmado';
        case '2':
          return 'Não reconhece o pedido';
        case '3':
          return 'Mercadoria não recebida';
        case '4':
          return 'Recebida com avaria';
        case '5':
          return 'Devolvida';
        case '6':
          return 'Recebida com devolução parcial';
        case '7':
          return 'Recebida e confirmada';
        case '8':
          return 'Pagamento Autorizado';
        default:
          return 'Não definido';
      }
    },

    async getOrders() {
      const response = await api.get('/orders');
      this.orders = response.data;
    },

    formatterValue(value) {
      return Intl.NumberFormat('pt-BR', {
        style: 'currency',
        currency: 'BRL',
        minimumFractionDigits: 2,
      }).format(value);
    },
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

.container-conteudo {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-top: 155px;
  margin-left: 80px;
}

.container-conteudo .container-text-proposta {
  margin-left: 25px;
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

.container-table {
  width: 100%;
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
  color: #727d94;
  font-family: 'DM Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 11px;
}

.container-table-row .value-positive {
  color: #00ad8c;
}
</style>
