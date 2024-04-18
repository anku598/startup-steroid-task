<template>
  <div class="card-container">
    <div class="card-header">
      <div class="card-title">Document</div>
      <div class="card-icon">icon</div>
    </div>

    <div class="card-body">
      <div class="total-number">146.00</div>

      <div class="the-percent-value">
        <span class="percent-icon"></span>
        <span>17% Since last week</span>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-container {
  //   max-width: 200px;
  width: 100%;
  border-radius: 20px;
  background: #fff;
  padding: 2rem;
  min-height: 30vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.total-number {
  font-size: 2rem;
  text-transform: capitalize;
  margin: 1rem 0;
}
</style>
