<template>
  <div class="page-container">
    <div class="left-container">
      <div class="information-card-container">
        <Card />
        <Card />
        <Card />
      </div>

      <div class="chart-section">
        <ChartCard />
        <ChartCard />
      </div>

      <SlotComponentTable>
        <template #header>
          <div class="header-information">
            <div class="left-part">
              <div class="card-title">Document</div>
              <div class="subtext">Document Tracking Information</div>
            </div>

            <div class="right-part">
              <div class="time-dropdown">Weekly</div>
            </div>
          </div>
        </template>

        <template #main>
          <Table />
        </template>
      </SlotComponentTable>
    </div>
    <div class="right-container">
      <PopularInfoCard />
      <PopularInfoCard />
    </div>
  </div>
</template>
<script setup>
import Card from "@/components/UI/Card.vue";
import ChartCard from "@/components/UI/ChartCard.vue";
import PopularInfoCard from "@/components/UI/PopularInfoCard.vue";
import SlotComponentTable from "@/components/UI/SlotComponentTable.vue";
import Table from "@/components/UI/Table.vue";
</script>

<style lang="scss" scoped>
.page-container {
  display: flex;
  gap: 1rem;
}
.left-container {
  flex: 4;
}

.information-card-container,
.chart-section {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
  margin-bottom: 2rem;
}

.right-container {
  flex: 1;
  background: #fff;
  padding: 2rem;
  border-radius: 20px;
  max-width: 350px;
  min-height: calc(100vh - 140px);
  max-width: 300px;
}

.header-information {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 2rem;
  .card-title {
    font-size: 1.5rem;
    font-weight: bold;
  }
}
</style>
