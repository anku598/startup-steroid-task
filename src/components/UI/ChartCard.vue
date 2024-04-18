<template>
  <div class="chart-card-container">
    <div class="card-header">
      <div class="card-title">Recent Workflow</div>
      <div class="the-percent-value">
        <span class="percent-icon"></span>
        <span>17% Since last week</span>
      </div>
    </div>

    <div class="card-body">
      <div class="total-number">
        <BarChart :chartData="testData" />
      </div>
    </div>
  </div>
</template>

<script>
import { Chart, registerables } from "chart.js";
import { defineComponent } from "vue";
import { BarChart } from "vue-chart-3";

Chart.register(...registerables);

export default defineComponent({
  name: "Home",
  components: { BarChart },
  setup() {
    const testData = {
      labels: ["Paris", "Nîmes", "Toulon", "Perpignan", "Autre"],
      datasets: [
        {
          data: [30, 40, 60, 70, 5],
          backgroundColor: [
            "#77CEFF",
            "#0079AF",
            "#123E6B",
            "#97B0C4",
            "#A5C8ED",
          ],
        },
      ],
    };

    return { testData };
  },
});
</script>

<style lang="scss" scoped>
.card-header {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
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
</style>
