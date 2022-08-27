<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref } from "vue";
import { onClickOutside } from "@vueuse/core";
import NavInput from "./NavInput.vue";

const isClicked = ref<boolean>(false);
const target = ref<any>(null);

const openWindow = (): void => {
  isClicked.value = true;
};

const exitWindow = (): void => {
  isClicked.value = false;
};

onClickOutside(target, (): void => {
  exitWindow();
});
const onKeyPress = (event: KeyboardEvent): void => {
  if (event.key !== "/") {
    return;
  }
  isClicked.value = true;
};
onMounted(() => {
  window.addEventListener("keypress", onKeyPress);
});
onBeforeUnmount(() => {
  window.removeEventListener("keypress", onKeyPress);
});
</script>

<template>
  <div class="relative">
    <div
      @click="openWindow"
      class="bg-[#EFF2F5] h-9 rounded-lg w-64 flex items-center justify-between px-3 hover:cursor-pointer"
    >
      <div class="flex">
        <img src="../../../assets/search.svg" alt="" />
        <p class="ml-2 text-[#A6B0C3] text-xs">Search</p>
      </div>
      <img src="../../../assets/slash.png" alt="" />
    </div>

    <NavInput @exit="exitWindow" v-if="isClicked" ref="target" />
  </div>
</template>
