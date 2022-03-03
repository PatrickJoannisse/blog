<template>
  <div class="dark:bg-gray-900">
    <SkipLink />
    <TopNav />
    <section class="max-w-screen-lg mx-auto px-4 py-4" id="content">
      <Nuxt />
    </section>
    <Footer />
  </div>
</template>

<script>
export default {
  head: {
    bodyAttrs: {
      class: "dark:bg-[#0e0e0e]",
    },
  },
};
</script>
