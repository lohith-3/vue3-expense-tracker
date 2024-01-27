<template>
  <div class="expense__tracker__container flex-container">
    <the-header />
    <the-balance :balance="balanceAmount" />
    <the-expenses :totalIncome="totalIncome" :totalExpense="totalExpense" />
    <transaction-list
      :transactions="transactions"
      @on-delete-transaction="onDeleteTransactionActionHandler"
    />
    <add-transction @add-transaction="addTransctionActionHandler" />
  </div>
</template>

<script>
import TheBalance from './components/TheBalance.vue'
import TheHeader from './components/TheHeader.vue'
import TheExpenses from './components/TheExpenses.vue'
import TransactionList from './components/TransactionList.vue'
import AddTransction from './components/AddTransction.vue'
import { ref, computed } from 'vue'
export default {
  components: {
    TheHeader,
    TheBalance,
    TheExpenses,
    TransactionList,
    AddTransction
  },
  setup() {
    const transactions = ref([
      {
        id: 'id' + Math.random().toString(16).slice(2),
        transactionName: 'Sneakers',
        transactionAmount: '-200'
      },
      {
        id: 'id' + Math.random().toString(16).slice(2),
        transactionName: 'PayCheck',
        transactionAmount: '900'
      },
      {
        id: 'id' + Math.random().toString(16).slice(2),
        transactionName: 'Course',
        transactionAmount: '500'
      }
    ])
    const totalIncome = computed(() => {
      return transactions.value.reduce((prev, curr) => {
        if (curr.transactionAmount.includes('-')) {
          return prev
        }
        return prev + +curr.transactionAmount
      }, 0)
    })
    const totalExpense = computed(() => {
      return transactions.value.reduce((prev, curr) => {
        if (!curr.transactionAmount.includes('-')) {
          return prev
        }
        return prev + +curr.transactionAmount.slice(1)
      }, 0)
    })
    const balanceAmount = computed(() => {
      return totalIncome.value - totalExpense.value
    })

    function addTransctionActionHandler(event) {
      const transaction = {
        id: 'id' + Math.random().toString(16).slice(2),
        ...event
      }
      transactions.value.push(transaction)
    }
    function onDeleteTransactionActionHandler(id) {
      if (!id) return

      transactions.value = transactions.value.filter((trans) => trans.id !== id)
    }
    return {
      transactions,
      totalExpense,
      totalIncome,
      balanceAmount,
      addTransctionActionHandler,
      onDeleteTransactionActionHandler
    }
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
