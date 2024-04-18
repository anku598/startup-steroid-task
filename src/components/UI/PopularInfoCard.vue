<template>
  <div class="popular-info-card">
    <div class="popular-info">
      <div class="title">Popular</div>
      <ul>
        <li>
          <div class="product-img">
            <img src="https://placehold.co/400" alt="" />
          </div>

          <div class="product-info">
            <div class="name">Gadget Converter</div>
            <div class="price">$250</div>
          </div>
        </li>

        <li>
          <div class="product-img">
            <img src="https://placehold.co/400" alt="" />
          </div>

          <div class="product-info">
            <div class="name">Gadget Converter</div>
            <div class="price">$250</div>
          </div>
        </li>

        <li>
          <div class="product-img">
            <img src="https://placehold.co/400" alt="" />
          </div>

          <div class="product-info">
            <div class="name">Gadget Converter</div>
            <div class="price">$250</div>
          </div>
        </li>

        <li>
          <div class="product-img">
            <img src="https://placehold.co/400" alt="" />
          </div>

          <div class="product-info">
            <div class="name">Gadget Converter</div>
            <div class="price">$250</div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.popular-info-card {
  background: #fff;
  margin-bottom: 3rem;
}
.title {
  margin-bottom: 2.2rem;
}
ul {
  margin-bottom: 2.2rem;
  li {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 1rem;
  }
}

.product-img {
  width: 50px;
  height: 50px;

  img {
    width: 100%;
    border-radius: 100%;
  }
}

.name {
  margin-bottom: 10px;
}
</style>
