<template>
  <div class="chart-card-container">
    <div class="card-header">
      <div class="card-title">
        <slot name="title"></slot>
      </div>
      <div class="the-percent-value">
        <span><i class="fa-solid fa-arrow-trend-up"></i>17%</span>
      </div>
    </div>

    <div class="card-body">
      <div class="total-number">
        <slot name="chart"></slot>
      </div>
    </div>
  </div>
</template>

<script></script>

<style lang="scss" scoped>
.card-header {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

.card-title {
  @include res-font(15, 22, 360, 1920);
  font-weight: 500;
  margin-bottom: 1.5rem;
}

.chart-card-container {
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

.the-percent-value {
  color: green;
}

i {
  margin-right: 15px;
}
</style>
