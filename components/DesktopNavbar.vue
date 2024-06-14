<script setup lang="ts">
const settings = useSettings();
const navigation = useNavigation();
const navItems = navigation.value?.data.links;
</script>
<template>
  <div class="navbar">
    <div class="items">
      <div class="logo"><PrismicImage :field="settings.data.logo" /></div>
      <div class="links">
        <div v-for="item in navItems" :key="item.label ?? ''">
          <PrismicLink class="link" :field="item.link">{{
            item.label
          }}</PrismicLink>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped lang="scss">
.navbar {
  z-index: 2;
  width: 100%;
  position: fixed;

  .items {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2.5rem;

    .logo {
      height: 7rem;

      img {
        height: 100%;
        width: auto;
      }
    }

    .links {
      display: flex;
      gap: 3rem;
      padding-bottom: 3.5rem;
    }
  }
}
</style>
