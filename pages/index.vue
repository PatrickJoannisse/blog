<template>
  <div class="space-y-4 divide-y divide-gray-700">
    <article
      v-for="(article, index) in articles"
      :key="article.slug"
      class="py-4 lg:flex"
    >
      <NuxtLink
        :to="'/posts/' + article.slug"
        :aria-label="'Read ' + article.title"
        v-if="article.img"
        class="block w-full bg-center bg-cover  h-44 lg:w-1/2 lg:h-auto rounded-t-md lg:rounded-r-none lg:rounded-l-md"
        :style="'background-image: url(\'' + article.img + '\')'"
      />
      <section :class="article.img ? 'w-full lg:w-1/2' : ''">
        <header>
          <h2
            class="px-4 pt-3 pb-2 text-3xl font-bold  dark:text-white dark:hover:text-gray-300"
          >
            <NuxtLink :to="'/posts/' + article.slug">{{
              article.title
            }}</NuxtLink>
          </h2>

          <p class="sr-only">Tags:</p>
          <ul class="inline-flex px-4 my-2 space-x-2">
            <li v-for="tag in article.tags" :key="tag">
              <NuxtLink :to="`/tags/${tag}/`">
                <tag>#{{ tag }}</tag></NuxtLink
              >
            </li>
          </ul>
        </header>
        <p class="px-4 pb-4 mt-3 leading-relaxed dark:text-gray-300">
          {{ article.description }}
        </p>
        <footer class="flex items-end px-4 pb-2 space-x-6 text-sm">
          <span class="dark:text-gray-400">{{
            formatDate(article.updatedAt)
          }}</span>
          <span class="dark:text-gray-400">
            {{ article.readingStats.text }}
          </span>
        </footer>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("articles", {
      deep: true,
    })
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
      .sortBy("createdAt", "desc")
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
