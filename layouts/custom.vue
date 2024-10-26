<script setup>
const props = defineProps({
  title: String,
});
</script>
<template>
  <div class="page">
    <div class="page-wrap _container">
      <TheTitle :text="props.title" />
      <slot />
    </div>
  </div>
</template>
<style lang="scss" scoped>
._container {
  width: 100%;
  padding-left: 32px;
  padding-right: 32px;
}
</style>
