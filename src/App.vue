<script setup>
import { ref } from 'vue'
import TheHeader from '@/components/TheHeader.vue'
import TheNav from '@/components/TheNav.vue'
import TheTimeline from '@/pages/TheTimeline.vue'
import TheActivities from '@/pages/TheActivities.vue'
import TheProgress from '@/pages/TheProgress.vue'
import { PAGE_ACTIVITIES, PAGE_PROGRESS, PAGE_TIMELINE } from './constants.js'
import { normalizePageHash, generateTimelineItems } from '@/functions.js'

const currentPage = ref(normalizePageHash())
const timelineItems = generateTimelineItems()

function goTo(page) {
  currentPage.value = page
}
</script>

<template>
  <the-header @go-to-timeline="goTo(PAGE_TIMELINE)" @go-to-progress="goTo(PAGE_PROGRESS)" />
  <main class="flex flex-col flex-grow">
    <the-timeline v-show="currentPage === PAGE_TIMELINE" :timeline-items="timelineItems" />
    <the-activities v-show="currentPage === PAGE_ACTIVITIES" />
    <the-progress v-show="currentPage === PAGE_PROGRESS" />
  </main>
  <the-nav :current-page="currentPage" @navigate="goTo($event)" />
</template>
