<template>
  <NuxtLink
    :to="to"
    class="inline-flex items-center px-4 py-2 space-x-2 transition duration-150 bg-transparent rounded-md  hover:bg-gray-400 dark:text-gray-300 dark:hover:text-gray-100 dark:hover:bg-gray-700"
  >
    <slot></slot>
  </NuxtLink>
</template>

<script>
export default {
  props: {
    to: String,
  },
};
</script>
