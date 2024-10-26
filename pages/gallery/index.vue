<script setup>
definePageMeta(transition);

watch(
  () => [general.isTransitionFinish, general.isPreloaderVisible],
  ([transitionFinish, preloaderVisibility]) => {
    if (transitionFinish && !preloaderVisibility) {
      contentAnimation({ type: "image", element: ".page-content__photo" });
    }
  }
);
</script>
<template>
  <div :class="general.pageBg">
    <NuxtLayout name="custom" page-name="gallery" title="gallery">
      <div class="page-content">
        <nuxt-link
          v-for="(_, i) in 1"
          class="page-content__photo hover-image"
          :to="`/gallery/${i + 1}`"
        >
          <img src="/photo.jpeg" alt="" />
        </nuxt-link>
        <nuxt-link
          v-for="(_, i) in 1"
          class="page-content__photo hover-image"
          :to="`/gallery/${i + 2}`"
        >
          <img src="/cat2.jpg" alt="" />
        </nuxt-link>
        <nuxt-link
          v-for="(_, i) in 1"
          class="page-content__photo hover-image"
          :to="`/gallery/${i + 3}`"
        >
          <img src="/kg1.jpg" alt="" />
        </nuxt-link>
        <nuxt-link
          v-for="(_, i) in 1"
          class="page-content__photo hover-image"
          :to="`/gallery/${i + 4}`"
        >
          <img src="/kg2.jpg" alt="" />
        </nuxt-link>
      </div>
    </NuxtLayout>
  </div>
</template>
<style lang="scss" scoped>
.page-content {
  display: flex;
  justify-content: center;
  width: 100%;
  align-items: flex-start;
}
</style>
