<template>
  <div class="dark:bg-gray-900">
    <SkipLinks />
    <header
      class="max-w-screen-lg pt-4 mx-auto text-center border-b border-transparent  dark:border-gray-700"
    >
      <NuxtLink
        to="/"
        class="inline-flex items-center pt-4 text-4xl font-extrabold  dark:text-white font-logo"
        >Patrick Joannisse</NuxtLink
      >
    </header>
    <Navbar />
    <section>
      <div class="max-w-screen-lg px-4 mx-auto my-6" id="content">
        <!--
        <NuxtLink
          to="/"
          class="inline-flex items-center space-x-2 transition duration-150 dark:text-gray-300 dark:hover:text-gray-100"
          ><svg
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
            />
          </svg>
          <span>Back</span>
        </NuxtLink> -->
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
