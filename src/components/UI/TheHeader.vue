<template>
  <div class="the-header">
    <h2>Overview</h2>
    <div class="navigation-info">
      <div class="profile-items">
        <div class="notification-icon">
          <i class="fa-regular fa-bell"></i>
        </div>

        <div class="profile-img">
          <img src="https://placehold.co/200" alt="Profile Image" />
        </div>
        <div class="role-name">Adminstator</div>
        <div class="dropdown-icon">
          <i class="fa-solid fa-caret-down"></i>
        </div>
      </div>

      <!-- <div class="dropdown-navbar">
        <div class="dropdown-item">Settings</div>
        <div class="dropdown-item">Logout</div>
      </div> -->
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.the-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding-bottom: 2rem;
  h2 {
    @include res-font(20, 50, 360, 1920);
  }
}

.notification-icon {
  width: 30px;
}

.profile-img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  overflow: hidden;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.profile-items {
  display: flex;
  gap: 1rem;
  align-items: center;
}
</style>
