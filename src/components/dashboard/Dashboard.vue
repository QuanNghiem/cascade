<template>
  <div class="container">
    <div class="subcontainer">
      <h1>Pending</h1>
      <div v-for="obj in bankData.Statement.NotSettled" :key="obj">
        <BankTrans :trans="obj" />
      </div>

      <h1>Transaction</h1>
      <div v-for="obj in bankData.Statement.Transactions" :key="obj">
        <BankTrans :trans="obj" />
      </div>
    </div>
  </div>
</template>

<script>
import data from "../../assets/data.json";
import BankTrans from "../dashboard/BankTrans.vue";

export default {
  name: "BankDashboard",
  components: {
    BankTrans,
  },
  props: {},
  data() {
    return {
      bankData: data,
      header: {
        "Transaction Type": "TransactionTypeId",
        "Merchant Name": "MerchantName",
        Amount: "Amount",
        "Starting Balance": "AvailableBalance",
        "Ending Balance": "AvailableBalance",
      },
    };
  },
};
</script>

<style scoped>
.container {
  /* width: 50vw; */
  display: flex;
  flex-direction: column;
  align-items: center;
}

.subcontainer {
  width: 50vw;
}
</style>