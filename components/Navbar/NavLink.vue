<template>
  <NuxtLink
    :to="to"
    class="inline-flex items-center px-2 py-1 space-x-2 border-b border-transparent  hover:border-gray-800 dark:text-gray-300 dark:hover:text-gray-100 dark:hover:border-gray-100"
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
