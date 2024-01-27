<template>
  <div class="balance__container">
    <p>YOUR BALANCE</p>
    <span>{{ balance }}$</span>
  </div>
</template>

<script>
export default {
  props: {
    balance: {
      type: Number,
      required: true,
      default: 0
    }
  },
  setup() {
    return {}
  }
}
</script>

<style scoped>
.balance__container {
  width: 400px;
}
.balance__container p,
.balance__container span {
  font-size: 1rem;
  font-weight: bold;
  color: #343a40;
}
.balance__container span {
  font-size: 2rem;
}
</style>
