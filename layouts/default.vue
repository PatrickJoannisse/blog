<template>
  <div class="bg-gray-50 dark:bg-gray-900">
    <SkipLink />
    <Navbar />
    <section class="max-w-screen-lg px-4 py-4 mx-auto" id="content">
      <Nuxt />
    </section>
    <Footer />
  </div>
</template>

<script>
export default {
  head: {
    bodyAttrs: {
      class: "bg-white dark:bg-[#0e0e0e]",
    },
  },
};
</script>
