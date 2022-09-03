<script setup>
import { ref, onMounted, computed } from "vue";

const count1 = ref(0);
const count2 = ref(0);

const increment = (which) => {
  if (which === 1) {
    count1.value++;
  } else {
    count2.value++;
  }
};

const decrement = (which) => {
  if (which === 1) {
    count1.value--;
  } else {
    count2.value--;
  }
};

onMounted(() => {
  console.log("mounted");

  // count.value = 100;
});

const sum = computed(() => count1.value + count2.value);
</script>

<template>
  <div
    class="
      min-h-screen
      gap-x-8
      w-full
      bg-slate-100
      flex
      justify-center
      items-center
    "
  >
    <div class="bg-white flex-1 max-w-md rounded-xl shadow-xl overflow-hidden">
      <h1 class="text-9xl font-semibold text-center text-gray-800 py-12">
        {{ count1 }}
      </h1>
      <div class="flex">
        <button
          class="
            bg-blue-600
            py-4
            font-mono
            text-center
            flex-1
            text-5xl text-white
            hover:bg-blue-700
          "
          @click="decrement(1)"
        >
          -
        </button>
        <button
          class="
            bg-blue-500
            py-4
            font-mono
            text-center
            flex-1
            text-5xl text-white
            hover:bg-blue-700
          "
          @click="increment(1)"
        >
          +
        </button>
      </div>
    </div>

    <div class="bg-white flex-1 max-w-md rounded-xl shadow-xl overflow-hidden">
      <h1 class="text-9xl font-semibold text-center text-gray-800 py-12">
        {{ count2 }}
      </h1>
      <div class="flex">
        <button
          class="
            bg-blue-600
            py-4
            font-mono
            text-center
            flex-1
            text-5xl text-white
            hover:bg-blue-700
          "
          @click="decrement(2)"
        >
          -
        </button>
        <button
          class="
            bg-blue-500
            py-4
            font-mono
            text-center
            flex-1
            text-5xl text-white
            hover:bg-blue-700
          "
          @click="increment(2)"
        >
          +
        </button>
      </div>
    </div>
    <div class="flex-1 text-center max-w-md text-9xl font-bold text-gray-800">
      = {{ sum }}
    </div>
  </div>
</template>