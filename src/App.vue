<template>
  <div class="expense__tracker__container flex-container">
    <the-header />
    <the-balance />
    <the-expenses />
    <transaction-list />
    <add-transction />
  </div>
</template>

<script>
import TheBalance from './components/TheBalance.vue'
import TheHeader from './components/TheHeader.vue'
import TheExpenses from './components/TheExpenses.vue'
import TransactionList from './components/TransactionList.vue'
import AddTransction from './components/AddTransction.vue'
export default {
  components: {
    TheHeader,
    TheBalance,
    TheExpenses,
    TransactionList,
    AddTransction
  },
  setup() {
    return {}
  }
}
</script>

<style scoped>
.expense__tracker__container {
  width: 1200px;
  margin: 1.5rem auto;
  align-items: center;
  gap: 1rem;
}
</style>
