<template>
  <div class="space-x-4 md:flex">
    <div class="w-3/4 space-y-4">
      <div
        v-for="article in articles"
        :key="article.slug"
        class="transition duration-150 bg-white border border-gray-300 rounded-md  dark:border-none hover:shadow-md dark:bg-gray-800"
      >
        <div
          v-if="article.img"
          class="w-full bg-center bg-cover h-52 rounded-t-md"
          :style="'background-image: url(\'' + article.img + '\')'"
        />
        <h2
          class="px-4 py-2 text-2xl font-bold  dark:text-white dark:hover:text-gray-300"
        >
          <NuxtLink :to="'/posts/' + article.slug">{{
            article.title
          }}</NuxtLink>
        </h2>

        <p v-if="!article.img" class="px-4 pb-4 dark:text-gray-300">
          {{ article.description }}
        </p>
        <div class="flex items-center px-4 pb-2 space-x-6 text-sm">
          <span class="dark:text-gray-400">{{
            formatDate(article.updatedAt)
          }}</span>
          <span class="dark:text-gray-400">
            {{ article.readingStats.text }}
          </span>
          <p class="sr-only">Tags:</p>
          <ul class="inline-flex my-2 space-x-2">
            <li v-for="tag in article.tags" :key="tag">
              <NuxtLink :to="`/tags/${tag}/`">
                <tag>#{{ tag }}</tag></NuxtLink
              >
            </li>
          </ul>
        </div>
      </div>
    </div>
    <aside class="w-1/4">I'm an aside</aside>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("articles", params.slug)
      .where({
        status: "published",
      })
      .only([
        "title",
        "description",
        "img",
        "slug",
        "tags",
        "updatedAt",
        "readingStats",
      ])
      .sortBy("createdAt", "asc")
      .fetch();

    return {
      articles,
    };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
};
</script>
