<script setup>
import { ref, reactive, onMounted, computed } from "vue";

const count = reactive({
  number1: 0,
  number2: 0,
});

const increment = (which) => {
  if (which === 1) {
    count.number1++;
  } else {
    count.number2++;
  }
};

const decrement = (which) => {
  if (which === 1) {
    count.number1--;
  } else {
    count.number2--;
  }
};

onMounted(() => {
  console.log("mounted");
});

const sum = computed(() => count.number1 + count.number2);
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
        {{ count.number1 }}
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
        {{ count.number2 }}
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