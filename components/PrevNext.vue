<template>
  <div class="grid grid-cols-2">
    <div class="w-full">
      <NuxtLink
        v-if="prev"
        :to="prev.slug"
        class="inline-flex items-center space-x-2 text-white"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-4 h-4 mt-0.5"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M10 19l-7-7m0 0l7-7m-7 7h18"
          /></svg
        ><span>Prev</span></NuxtLink
      >
    </div>
    <div class="w-full text-right">
      <NuxtLink
        v-if="next"
        :to="next.slug"
        class="inline-flex items-center space-x-2 text-white"
      >
        <span>Next</span>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="w-4 h-4 mt-0.5"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M14 5l7 7m0 0l-7 7m7-7H3"
          />
        </svg>
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  name: "PrevNext",
  props: {
    prev: Object,
    next: Object,
  },
};
</script>
