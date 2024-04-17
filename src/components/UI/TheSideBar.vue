<template>
  <div class="sidebar-container">
    <div class="sidebar">
      <a class="logo" href="#">CRM.io</a>

      <nav>
        <router-link class="main-link" to="/">Dashboard</router-link>
        <div class="nav-category" v-for="(nav, idx) in navItems" :key="idx">
          <h2 class="category-title">{{ nav.title }}</h2>
          <ul class="category-list">
            <li
              class="category-item"
              v-for="(sub_item, sidx) in nav.children"
              :key="sidx"
            >
              <div class="icon">x</div>
              <router-link :to="sub_item.path" class="category-link">{{
                sub_item.title
              }}</router-link>
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const navItems = ref([
  {
    title: "Management",
    children: [
      {
        title: "Document",
        icon: "x",
        path: "/dashboard",
      },
      {
        title: "Contact",
        icon: "x",
        path: "/customers",
      },
      {
        title: "Prospect",
        icon: "x",
        path: "/products",
      },
      {
        title: "Workflow",
        icon: "x",
        path: "/orders",
      },
    ],
  },
  {
    title: "Connection",
    children: [
      {
        title: "Chat Integration",
        icon: "x",
        path: "/",
      },
      {
        title: "marketing automation",
        icon: "x",
        path: "/customers",
      },
      {
        title: "Email Integration",
        icon: "x",
        path: "/products",
      },
    ],
  },

  {
    title: "Customer",
    children: [
      {
        title: "Transaction",
        icon: "x",
        path: "/dashboard",
      },
      {
        title: "Maintanance",
        icon: "x",
        path: "/customers",
      },
    ],
  },
]);
</script>

<style lang="scss" scoped>
.sidebar-container {
  background-color: #041737;
  width: 100%;
  height: 100vh;
  padding: 2.2rem 2rem;
  color: white;
  max-width: 300px;
}

.logo {
  font-size: 1.8rem;
  font-weight: bold;
  color: #ec8660;
  text-decoration: none;
  display: block;
  margin-bottom: 2rem;
  font-style: italic;
}

.main-link {
  font-size: 1.2rem;
  color: #fff;
}

.nav-category {
  padding: 1.5rem 0;
  border-bottom: 1px solid rgba($color: #fff, $alpha: 0.3);
  &:last-child {
    border-bottom: none;
  }
  .category-title {
    font-size: 1.2rem;
    margin-bottom: 2rem;
    color: lightgray;
    text-transform: capitalize;
  }
  .category-item {
    display: flex;
    align-items: center;
    margin-bottom: 1.2rem;
    gap: 10px;
    .category-link {
      font-size: 1rem;
      color: white;
    }
  }
}
</style>
