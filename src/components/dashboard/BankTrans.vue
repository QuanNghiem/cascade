<template>
  <div>
    <div class="trans_container" @click="open = !open">
      <div class="trans_item">
        <p class="title">{{ trans.MerchantName }}</p>
        <p class="subTitle">
          {{ moment(trans.TransactionDate).format("MMM Do YY") }}
        </p>
      </div>

      <div class="trans_item2">
        <p class="title">- {{ trans.Amount }}</p>
        <p class="subTitle">{{ trans.AvailableBalance - trans.Amount }}</p>
      </div>
    </div>
    <div v-show="open">
      <div class="trans_container_info">
        <div class="trans_item_info">
          <p class="moreInfo">Merchant ID: {{ trans.MerchantId }}</p>
          <p class="moreInfo">Description: {{ trans.Description }}</p>
        </div>

        <div class="trans_item2_info">
          <p class="moreInfo">
            Transaction Type: {{ trans.TransactionTypeId }}
          </p>
          <p class="moreInfo">Account No: {{ trans.AccountNumber }}</p>
        </div>

        <!-- <div class="trans_item2">
          <p class="title">- {{ trans.Amount }}</p>
          <p class="subTitle">{{ trans.AvailableBalance - trans.Amount }}</p>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";

export default {
  name: "BankTrans",
  props: {
    trans: {},
  },
  data() {
    return {
      open: false,
    };
  },
  methods: {
    moment,
  },
};
</script>

<style scoped>
.trans_container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  border-top: 0.1rem solid #494949;
  border-left: 0.1rem solid #494949;
  border-right: 0.1rem solid #494949;
  border-bottom: 0.05rem solid #494949;
  cursor: pointer;
  transition: 0.2s ease-out;
}

.trans_container:hover {
  background-color: #e3e3e3;
  transition: 0.2s ease-out;
}

.trans_item {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin: 0.5rem;
}

.trans_container_info {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  background-color: #f5f5f5;
  border-left: 0.05rem dotted #494949;
  border-right: 0.05rem dotted #494949;
}

.trans_item_info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin: 0.5rem;
  margin-right: 2rem;
}

.trans_item2_info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  margin: 0.5rem;
}

.trans_item2 {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  margin: 0.5rem;
}

.title {
  font-size: 1.2rem;
}

.moreInfo {
  font-size: 1rem;
}

.subTitle {
  font-size: 1rem;
  font-style: italic;
  font-weight: 250;
}

p {
  padding: 0.05rem 0rem;
  margin: 0;
}
</style>