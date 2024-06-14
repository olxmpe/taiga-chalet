<script setup lang="ts"></script>
<template>
  <div class="app-container">
    <div class="navbar desktop">
      <DesktopNavbar />
    </div>
    <slot />
  </div>
</template>
<style scoped lang="scss">
.app-container {
  width: 100vw;
  height: 100vh;

  .navbar {
    max-width: 100%;
  }
}
</style>
