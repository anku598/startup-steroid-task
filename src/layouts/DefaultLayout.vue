<template>
  <div class="default-container">
    <TheSideBar />
    <div class="main-content">
      <TheHeader />
      <RouterView />
    </div>
  </div>
</template>

<script setup>
import TheHeader from "@/components/UI/TheHeader.vue";
import TheSideBar from "@/components/UI/TheSideBar.vue";
</script>

<style lang="scss" scoped>
.default-container {
  display: flex;
  gap: 2rem;
  background: #f0f1f3;
}

.main-content {
  padding-top: 2rem;
  padding-right: 2rem;
  flex: 1;
}
</style>
