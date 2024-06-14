<script setup lang="ts">
const navigation = useNavigation();
const navItems = navigation.value?.data.links;
</script>
<template>
  <div class="navbar">
    <div class="items">
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
.link {
  line-height: 2rem;
}
</style>
