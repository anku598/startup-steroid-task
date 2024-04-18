<template>
  <div class="the-header">
    <h2>Overview</h2>
    <div class="navigation-info">
      <div class="profile-items">
        <div class="notification-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
          >
            <path
              d="M5 18H19V11.0314C19 7.14806 15.866 4 12 4C8.13401 4 5 7.14806 5 11.0314V18ZM12 2C16.9706 2 21 6.04348 21 11.0314V20H3V11.0314C3 6.04348 7.02944 2 12 2ZM9.5 21H14.5C14.5 22.3807 13.3807 23.5 12 23.5C10.6193 23.5 9.5 22.3807 9.5 21Z"
            ></path>
          </svg>
        </div>

        <div class="profile-img">
          <img src="https://placehold.co/200" alt="Profile Image" />
        </div>
        <div class="role-name">Adminstator</div>
        <div class="dropdown-icon">ico</div>
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
    // @include res-font(20, 50, 360, 1920);
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
