<template>
  <div class="dark:bg-gray-900">
    <SkipLink />
    <Navbar />
    <section>
      <div class="max-w-screen-lg px-4 mx-auto my-6" id="content">
        <NuxtLink
          to="/"
          class="transition duration-150  dark:text-gray-300 dark:hover:text-gray-100"
          >← Back
        </NuxtLink>
      </div>
      <Nuxt />
    </section>
    <Footer />
  </div>
</template>

<script>
export default {
  head: {
    bodyAttrs: {
      class: "bg-gray-50 dark:bg-[#0e0e0e]",
    },
  },
};
</script>
