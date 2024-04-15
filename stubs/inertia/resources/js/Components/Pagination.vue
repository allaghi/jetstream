<script setup>
import { Link } from '@inertiajs/vue3'
defineProps({
  links: Array,
});
</script>

<template>
  <div v-if="links.length > 3">
    <div class="flex flex-wrap -mb-1">
      <template v-for="(link, key) in links">
        <div v-if="link.url === null" :key="key" class="mb-1 mr-1 px-4 py-3 bg-white text-gray-500 text-sm leading-4 border border-slate-200 rounded" v-html="link.label" />
        <Link v-else :key="`link-${key}`" class="mb-1 mr-1 px-4 py-3 focus:text-indigo-500 text-sm leading-4 hover:bg-slate-800 hover:text-white border focus:border-indigo-500 rounded bg-white" :class="{ 'bg-slate-900 text-white': link.active }" :href="link.url" v-html="link.label" />
      </template>
    </div>
  </div>
</template>
