<template>
  <a
    :href="this.href"
    class="inline-flex items-center justify-center w-full px-3 py-2 space-x-4 text-center text-white transition duration-150 bg-gray-700  md:text-gray-500 md:bg-transparent md:w-auto hover:text-gray-100"
  >
    <slot></slot>
  </a>
</template>
<script>
export default {
  name: "SocialLink",
  props: {
    href: String,
  },
};
</script>
