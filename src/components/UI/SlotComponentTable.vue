<template>
  <div class="slot-comp-container">
    <header>
      <slot name="header"></slot>
    </header>

    <main>
      <slot name="main"></slot>
    </main>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.slot-comp-container {
  background: #fff;
  padding: 2.5rem;
  border-radius: 20px;
  //   box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
</style>
