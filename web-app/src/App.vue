<script setup lang="ts">
import data from "./data/calendarData.json";
import type {ICalendar} from "./data/calendar-interface.ts";
import {onMounted, ref} from "vue";

onMounted(() => {

})

const calendarData = ref<ICalendar[]>(data);

</script>

<template>
  <div v-for="month in calendarData" :key="month.name">
    <div>{{month.name}}</div>
    <div class="flex">
      <div v-for="col in 37" :key="col" class="border-2 border-black w-32 h-32">
        <div v-if="col >= month.weekOffset && col <= month.dayCount + month.weekOffset -1">{{col.valueOf() - month.weekOffset +1 }}</div>
      </div>
    </div>

  </div>

</template>

<style scoped>

</style>
