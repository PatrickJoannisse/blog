<template>
  <div>
    <div
      class="max-w-screen-lg px-4 mx-auto my-6 prose  md:prose-md lg:prose-lg dark:prose-invert dark:prose-a:text-indigo-400 dark:hover:prose-a:text-indigo-500 prose-a:transition prose-a:duration-150"
    >
      <nuxt-content :document="uses" />
    </div>
    <div class="max-w-screen-lg px-4 mx-auto my-6" id="content">
      <AuthorCard v-if="uses.authorcard" />
    </div>
  </div>
</template>
<script>
export default {
  layout: "BlogPost",
  async asyncData({ $content, params }) {
    const uses = await $content("uses").fetch();
    return { uses };
  },
};
</script>
