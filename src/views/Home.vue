<template>
  <div class="page-container">
    <div class="left-container">
      <div class="information-card-container">
        <Card
          v-for="(data, idx) in CardData"
          :key="'data' + idx"
          :card-data="data"
        />
      </div>

      <div class="chart-section">
        <ChartCard>
          <template #title> Recent Workflow </template>
          <template #chart>
            <LineChart :chartData="testData" :options="options" />
          </template>
        </ChartCard>

        <ChartCard>
          <template #title> Recent Marketing </template>
          <template #chart>
            <BarChart :chartData="testData" :options="options" />
          </template>
        </ChartCard>
      </div>

      <SlotComponentTable>
        <template #header>
          <div class="header-information">
            <div class="left-part">
              <div class="card-title">Document</div>
              <div class="subtext">Document Tracking Information</div>
            </div>

            <div class="right-part">
              <div class="time-dropdown" @click="showDropdown = !showDropdown">
                <p>{{ selectedOption }}</p>
                <i class="fa-solid fa-caret-down"></i>
                <ul v-if="showDropdown">
                  <li @click="selectOption('Weekly')">Weekly</li>
                  <li @click="selectOption('Monthly')">Monthly</li>
                  <li @click="selectOption('Yearly')">Yearly</li>
                </ul>
              </div>
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

import { defineComponent, ref } from "vue";

import { Chart, registerables } from "chart.js";
import { BarChart, LineChart } from "vue-chart-3";

Chart.register(...registerables);

defineComponent({
  name: "Home",
  components: { BarChart },
});

const testData = {
  labels: ["Paris", "Nîmes", "Toulon", "Perpignan", "Autre"],
  datasets: [
    {
      data: [30, 40, 60, 70, 5],
      backgroundColor: ["#1095c4", "#1095c4", "#1095c4", "#1095c4", "#1095c4"],
    },
  ],
};

const options = {
  responsive: true,
  borderColor: "#1095c4",
  borderWidth: 1,
  maintainAspectRatio: false,

  scales: {
    y: {
      beginAtZero: true,
    },
  },
};

const CardData = ref([
  {
    title: "Document",
    icon: `<i class="fa-regular fa-file"></i>`,
    price: "140.00",
    percent: "17%",
  },

  {
    title: "Contact",
    icon: `<i class="fa-regular fa-address-book"></i>`,
    price: "1400",
    percent: "17%",
  },

  {
    title: "Email",
    icon: `<i class="fa-regular fa-envelope"></i>`,
    price: "150.700",
    percent: "17%",
  },
]);

const showDropdown = ref(false);
const selectedOption = ref("Weekly");

const toggleDropdown = () => {
  showDropdown.value = !showDropdown.value;
};

const selectOption = (option) => {
  selectedOption.value = option;
  showDropdown.value = false;
};
</script>

<style lang="scss" scoped>
.page-container {
  display: flex;
  gap: 1rem;
  flex-direction: column;
  @include mediaXl {
    flex-direction: row;
  }
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
  width: 100%;
  background: #fff;
  padding: 2rem;
  border-radius: 20px;
  max-width: 100%;
  @include mediaXl {
    flex: 1;

    max-width: 350px;
    min-height: calc(100vh - 140px);
    max-width: 300px;
  }
}

.header-information {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 2rem;
  .card-title {
    @include res-font(17, 30, 360, 1920);
    font-weight: 700;
    margin-bottom: 15px;
  }

  .subtext {
    color: rgba($color: #000, $alpha: 0.5);
    @include res-font(14, 18, 360, 1920);
    font-weight: 500;
  }
}

.time-dropdown {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem;
  border-radius: 10px;
  background: #f5f5f5;
  cursor: pointer;
  position: relative;
  p {
    @include res-font(14, 18, 360, 1920);
    font-weight: 500;
  }
}

.time-dropdown {
  ul {
    position: absolute;
    background-color: #f5f5f5;
    border-radius: 10px;
    padding: 5px;
    list-style-type: none;
    margin: 0;
    top: 106%;
    right: 0%;
    z-index: 1000;
    /* max-width: 300px; */
    width: 200px;

    li {
      padding: 1rem;
      @include res-font(14, 18, 360, 1920);
      font-weight: 500;
      color: rgba($color: #000000, $alpha: 0.8);
    }
  }
}
</style>
