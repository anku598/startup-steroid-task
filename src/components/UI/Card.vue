<template>
  <div class="card-container">
    <div class="card-header">
      <div class="card-title">{{ cardData.title }}</div>
      <div class="card-icon" v-html="cardData.icon"></div>
    </div>

    <div class="card-body">
      <div class="total-number">{{ cardData.price }}</div>

      <div class="the-percent-value">
        <span class="percent-icon"></span>
        <div>
          <span class="value-style"
            ><i class="fa-solid fa-arrow-trend-up"></i>
            {{ cardData.percent }}</span
          >
          Since last week
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// will take props as cardData
defineProps(["cardData"]);
</script>

<style lang="scss" scoped>
.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-title {
  @include res-font(15, 22, 360, 1920);
  font-weight: 500;
}
.card-icon {
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 100%;
  background: #daecfd;
  font-size: 1.5rem;
}

.card-container {
  //   max-width: 200px;
  width: 100%;
  border-radius: 20px;
  background: #fff;
  padding: 2rem;
  min-height: 25vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.total-number {
  @include res-font(14, 24, 360, 1920);
  font-weight: 700;
  text-transform: capitalize;
  margin: 1rem 0;
  margin-bottom: 1.5rem;
}

.value-style {
  color: green;
  margin-right: 15px;
}
</style>
