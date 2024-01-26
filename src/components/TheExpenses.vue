<template>
  <div class="expenses__container">
    <div class="income__balance">
      <p>INCOME</p>
      <span class="positive">+1400$</span>
    </div>
    <div class="vertical__line"></div>
    <div class="expenses__balance">
      <p>EXPENSE</p>
      <span class="negative">-300$</span>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    return {}
  }
}
</script>

<style scoped>
.expenses__container {
  width: 400px;
  height: 100px;
  background: #fefefe;
  box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  border-radius: 5px;

  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
}
.vertical__line {
  width: 2px;
  height: 65px;
  background: #ced4da;
}
.income__balance p,
.expenses__balance p {
  font-weight: bold;
  color: #495057;
  margin-bottom: 2px;
}
.positive {
  color: #37b24d;
}
.negative {
  color: #e03131;
}
</style>
