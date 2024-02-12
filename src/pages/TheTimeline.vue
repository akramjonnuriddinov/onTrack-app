<script setup>
//
</script>

<template>
  <div class="mt-7">
    <ul>
      <li
        v-for="i in [0, 1, 2, 3, 4, 5]"
        :key="i"
        class="relative flex flex-col gap-2 px-4 py-10 border-t border-gray-200"
      >
        <a
          href="#"
          class="absolute px-2 font-mono text-lg text-gray-500 -translate-x-1/2 bg-gray-100 rounded -top-4 left-1/2"
          >{{ i }} : 00</a
        >
      </li>
    </ul>
  </div>
</template>
