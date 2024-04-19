<template>
  <div class="popular-info-card">
    <div class="popular-info">
      <div class="title">Popular Product</div>
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
  @include res-font(18, 24, 360, 1920);
  color: #2b2b2b;
  font-weight: 700;
}
ul {
  margin-bottom: 2.2rem;
  li {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    margin-bottom: 1.5rem;
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
  @include res-font(14, 18, 360, 1920);
  color: #2b2b2b;
  font-weight: 700;
}

.price {
  color: rgba($color: #000000, $alpha: 0.5);
}
</style>
