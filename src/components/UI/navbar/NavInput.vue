<script setup lang="ts">
import { onMounted, ref } from "vue";
const emit = defineEmits(["exit"]);
const input = ref<any>(null);

onMounted(() => {
  input.value.focus();
});
</script>

<template>
  <div
    class="w-96 h-40 absolute top-0 bg-white rounded-lg right-0 border shadow-md"
  >
    <div class="p-2 flex items-center">
      <img src="../../../assets/search.svg" alt="" />
      <input
        type="text"
        class="form-control block w-full px-3 py-1.5 text-sm font-normal text-[#A6B0C3] bg-white bg-clip-padding rounded transition ease-in-out m-0 focus:text-gray-700 focus:outline-none"
        placeholder="Search"
        ref="input"
      />
      <i class="hover:cursor-pointer" @click="emit('exit')">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="#A6B0C3"
          class="w-6 h-6"
        >
          <path
            fill-rule="evenodd"
            d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25zm-1.72 6.97a.75.75 0 10-1.06 1.06L10.94 12l-1.72 1.72a.75.75 0 101.06 1.06L12 13.06l1.72 1.72a.75.75 0 101.06-1.06L13.06 12l1.72-1.72a.75.75 0 10-1.06-1.06L12 10.94l-1.72-1.72z"
            clip-rule="evenodd"
          />
        </svg>
      </i>
    </div>
  </div>
</template>
