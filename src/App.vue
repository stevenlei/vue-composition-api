<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<template>
  <div
    class="min-h-screen w-full bg-slate-100 flex justify-center items-center"
  >
    <div class="bg-white flex-1 max-w-md rounded-xl shadow-xl overflow-hidden">
      <h1 class="text-9xl font-semibold text-center text-gray-800 py-12">
        {{ count }}
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
          @click="count--"
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
          @click="count++"
        >
          +
        </button>
      </div>
    </div>
  </div>
</template>