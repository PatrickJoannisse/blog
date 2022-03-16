<template>
  <div class="bg-gray-50 dark:bg-gray-900">
    <SkipLink />
    <header class="max-w-screen-lg pt-4 mx-auto text-center">
      <NuxtLink
        to="/"
        class="
          text-4xl
          lg:text-[4em]
          items-center
          inline-flex
          py-4
          font-extrabold
          dark:text-white
          font-logo
        "
        >Red Tape &amp; Dragons</NuxtLink
      >
    </header>
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
