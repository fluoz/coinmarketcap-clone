<script setup lang="ts">
import NavItems from "./NavItems.vue";
import NavSearch from "./NavSearch.vue";
</script>

<template>
  <nav class="w-full border-b border-slate-200">
    <div
      class="container mx-auto px-4 flex h-full items-center justify-between"
    >
      <div class="flex">
        <img src="../../../assets/Frame.svg" alt="" />
        <NavItems />
      </div>
      <NavSearch />
    </div>
  </nav>
</template>

<style scoped>
nav {
  height: 72px;
}
</style>
