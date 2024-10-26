<script setup>
definePageMeta(transition);

watch(
  () => [general.isTransitionFinish, general.isPreloaderVisible],
  ([transitionFinish, preloaderVisibility]) => {
    if (transitionFinish && !preloaderVisibility) {
      contentAnimation({ type: "text", element: ".page-content__block-text" });
      contentAnimation({
        type: "image",
        element: ".page-content__block-photo",
      });
      contentAnimation({ type: "text", element: ".page-next__project" });
    }
  }
);
</script>

<template>
  <div :class="general.pageBg">This is project 1 content</div>
</template>
