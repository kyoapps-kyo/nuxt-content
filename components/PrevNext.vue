<template>
  <div v-if="prev || next" class="flex justify-between">
    <NuxtLink
      v-if="prev"
      :to="{ name: 'articles-slug', params: { slug: prev.slug } }"
      :class="linkStyles"
    >
      {{ prev.title }}
    </NuxtLink>
    <span v-else>&nbsp;</span>
    <NuxtLink
      v-if="next"
      :to="{ name: 'articles-slug', params: { slug: next.slug } }"
      :class="linkStyles"
    >
      {{ next.title }}
    </NuxtLink>
    <span v-else>&nbsp;</span>
  </div>
</template>

<script>
export default {
  name: 'PrevNext',
  props: {
    prev: {
      type: Object,
      default: null,
    },
    next: {
      type: Object,
      default: null,
    },
  },
  computed: {
    linkStyles() {
      return 'bg-teal-400 dark:bg-violet-800 text-white px-4 py-1 rounded-md shadow-lg hover:bg-teal-600 dark:hover:bg-violet-900 transform duration-500 ease-in-out'
    },
  },
}
</script>
