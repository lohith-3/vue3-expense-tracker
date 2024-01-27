<template>
  <div class="add__transaction__container flex-container">
    <p>Add Transaction</p>
    <div class="horizantal__line"></div>
    <form class="add__form">
      <label for="text">Text</label>
      <input type="text" name="text" id="text" placeholder="Enter Text" autocomplete="off" />
      <label for="amout">Amount (negative - expense, positive + income)</label>
      <input type="text" name="amount" id="amount" placeholder="Enter Amount" autocomplete="off" />
      <button class="add__btn">Add Transaction</button>
    </form>
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
.add__transaction__container {
  width: 400px;
  align-items: flex-start;
  gap: 12px;
}
.add__form {
  display: flex;
  flex-direction: column;
  gap: 12px;
  width: 100%;
}
input[type='text'] {
  padding: 8px 12px;
  outline: none;
  border: 1px solid #e9ecef;
  border-radius: 2px;

  font-family: 'Roboto Mono', monospace;
}
input[type='text']:focus,
input[type='text']:active {
  outline: none;
}
.add__btn {
  appearance: none;
  -webkit-appearance: none;

  padding: 8px 12px;
  outline: none;
  border: none;
  background: slateblue;
  color: #fefefe;
  cursor: pointer;
  font-family: inherit;
  border-radius: 2px;
}
</style>
