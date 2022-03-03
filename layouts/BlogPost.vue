<template>
  <div class="dark:bg-gray-900">
    <SkipLink />
    <TopNav />
    <section>
      <div class="max-w-screen-lg mx-auto px-4 my-6" id="content">
        <NuxtLink to="/" class="dark:text-gray-300">← Back </NuxtLink>
      </div>
      <Nuxt />
    </section>
    <Footer />
  </div>
</template>

<script>
export default {
  head() {},
};
</script>
