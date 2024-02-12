<script setup>
const timelineItems = []

for (let hour = 0; hour < 24; hour++) {
  timelineItems.push({ hour })
}
</script>

<template>
  <div class="mt-7">
    <ul>
      <li
        v-for="{ hour } in timelineItems"
        :key="hour"
        class="relative flex flex-col gap-2 px-4 py-10 border-t border-gray-200"
      >
        <a
          href="#"
          class="absolute px-2 font-mono text-lg text-gray-500 -translate-x-1/2 bg-gray-100 rounded -top-4 left-1/2"
          >{{ hour }} : 00</a
        >
      </li>
    </ul>
  </div>
</template>
