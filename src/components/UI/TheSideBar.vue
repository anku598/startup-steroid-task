<template>
  <div>
    <div class="sidebar-container" :class="{ 'sidebar-open': isSidebarOpen }">
      <div class="close-icon" @click="toggleSidebar">
        <i class="fa-solid fa-xmark"></i>
      </div>
      <div class="sidebar">
        <a class="logo" href="#">CRM.io</a>

        <nav>
          <router-link class="main-link" to="/">
            <i class="fa-solid fa-table-cells-large"></i>
            <p>Dashboard</p>
          </router-link>
          <div class="nav-category" v-for="(nav, idx) in navItems" :key="idx">
            <h2 class="category-title">{{ nav.title }}</h2>
            <ul class="category-list">
              <li
                class="category-item"
                v-for="(sub_item, sidx) in nav.children"
                :key="sidx"
              >
                <div class="icon" v-html="sub_item.icon"></div>
                <router-link :to="sub_item.path" class="category-link">{{
                  sub_item.title
                }}</router-link>
              </li>
            </ul>
          </div>
        </nav>
      </div>
    </div>

    <div class="burger-menu-icon" @click="toggleSidebar">
      <i class="fa-solid fa-bars"></i>
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
        icon: `<i class="fa-regular fa-file"></i>`,
        path: "/",
      },
      {
        title: "Contact",
        icon: `<i class="fa-regular fa-address-book"></i>`,
        path: "/",
      },
      {
        title: "Prospect",
        icon: `<i class="fa-regular fa-file"></i>`,
        path: "/",
      },
      {
        title: "Workflow",
        icon: `<i class="fa-solid fa-briefcase"></i>`,
        path: "/",
      },
    ],
  },
  {
    title: "Connection",
    children: [
      {
        title: "Chat Integration",
        icon: `<i class="fa-regular fa-comment"></i>`,
        path: "/",
      },
      {
        title: "marketing automation",
        icon: `<i class="fa-solid fa-people-group"></i>`,
        path: "/",
      },
      {
        title: "Email Integration",
        icon: `<i class="fa-regular fa-envelope"></i>`,
        path: "/products",
      },
    ],
  },

  {
    title: "Customer",
    children: [
      {
        title: "Transaction",
        icon: `<i class="fa-regular fa-envelope"></i>`,
        path: "/",
      },
      {
        title: "Maintanance",
        icon: `<i class="fa-solid fa-screwdriver-wrench"></i>`,
        path: "/customers",
      },
    ],
  },
]);

const isSidebarOpen = ref(false);

const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value;
};
</script>

<style lang="scss" scoped>
.sidebar-container {
  background-color: #041737;
  width: 100%;
  height: 100vh;
  padding: 2.2rem 2rem;
  color: white;
  max-width: 300px;
  position: sticky;
  top: 0;
  display: block;
  @include media992px {
    position: fixed;
    left: 0;
    top: 0;
    z-index: 1000;
    width: 100%;
    max-width: 100%;
    // display: none;
    transform: translateX(-100%);
    transition: transform 0.3s ease;
  }
}

.close-icon {
  display: none;
  @include media992px {
    display: block;
    position: fixed;
    right: 20px;
    color: #fff;
    i {
      font-size: 1.4rem;
    }
  }
}

.sidebar-open {
  // Slide the sidebar-container in from the left
  transform: translateX(0);
  display: block;
}

.burger-menu-icon {
  display: none;
  @include media992px {
    display: block;
    position: fixed;
    top: 0px;
    left: 0px;
    background: #041737;
    padding: 1rem;
    color: #fff;
  }
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
  display: flex;
  gap: 0.7rem;
  align-items: center;
  background: #3963ad;
  padding: 1rem;
  border-radius: 15px;
}

.nav-category {
  padding: 1.5rem 0;
  border-bottom: 1px solid rgba($color: #fff, $alpha: 0.3);
  &:last-child {
    border-bottom: none;
  }
  .category-title {
    @include res-font(14, 18, 360, 1920);
    letter-spacing: 0.7px;
    margin-bottom: 2rem;
    color: rgba($color: #fff, $alpha: 0.3);
    text-transform: capitalize;
  }
  .category-item {
    display: flex;
    align-items: center;
    margin-bottom: 1.2rem;
    gap: 10px;
    .category-link {
      @include res-font(13, 15, 360, 1920);
      letter-spacing: 0.6px;
      color: white;
    }
  }
}
</style>
