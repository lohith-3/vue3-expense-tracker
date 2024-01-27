<template>
  <div class="transaction__container flex-container">
    <p>History</p>
    <div class="horizantal__line"></div>
    <div class="transaction__list flex-container">
      <div class="transaction negative__border">
        <p>Sneakers</p>
        <span>-200$</span>
        <div class="delete__transaction">&#10006;</div>
      </div>
      <div class="transaction positive__border">
        <p>Paycheck</p>
        <span>-900$</span>
        <div class="delete__transaction">&#10006;</div>
      </div>
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
.transaction__container {
  width: 400px;
  align-items: flex-start;
  gap: 12px;
}
.transaction__list {
  width: 100%;
  align-items: flex-start;
  gap: 14px;
}
.transaction {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  background: #fefefe;
  padding: 8px 12px;
  border-color: #dee2e6;

  position: relative;
  cursor: pointer;
}
.delete__transaction {
  position: absolute;
  top: 0;
  left: 0;
  background: red;
  color: #fefefe;
  border-radius: 2px;
  padding: 0px 5px;
  margin: 0;

  opacity: 0;

  transform: translate(-25px, 6px);
  /* animation: name duration timing-function delay iteration-count direction fill-mode; */
  transition: opacity 250ms ease-in-out;
}
.transaction:hover .delete__transaction {
  opacity: 1;
}

.transaction p {
  font-family: 'Roboto Mono', monospace;
}
.positive__border {
  border-right: 5px solid #37b24d;
}
.negative__border {
  border-right: 5px solid #c92a2a;
}
</style>
