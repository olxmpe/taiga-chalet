<script setup lang="ts">
import { type Content } from "@prismicio/client";

defineProps(
  getSliceComponentProps<Content.LandingPageSlice>([
    "slice",
    "index",
    "slices",
    "context",
  ])
);

const settings = useSettings();
</script>
<template>
  <div
    class="container"
    :style="{
      background: `linear-gradient(rgba(0, 0, 0, 0.35), rgba(0, 0, 0, 0.35)), url(${slice.primary.background_image.url})`,
    }"
  >
    <div class="content">
      <div class="mobile">
        <div class="logo"><PrismicImage :field="settings.data.logo" /></div>
      </div>
      <PrismicRichText :field="slice.primary.text" class="text" />
      <div class="mobile mobile-nav">
        <MobileNav />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  position: fixed;
  width: 100%;
  height: 100%;
  background-size: cover !important;
  background-position: 35% !important;
  background-repeat: no-repeat;

  .content {
    @media (max-width: 800px) {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      text-align: center;

      .mobile-nav {
        padding: 1rem 0;
      }
      .logo {
        height: 10rem;

        img {
          height: 100%;
          width: auto;
        }
      }
    }

    .text {
      line-height: 1.7rem;
      color: var(--color-light-background);

      @media (min-width: 800px) {
        position: absolute;
        top: 35%;
        left: 25%;
      }
    }
  }
}
</style>
