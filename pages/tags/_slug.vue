<template>
  <section>
    <header>
      <h1 class="text-3xl font-extrabold leading-loose dark:text-white">
        Posts about #{{ slug }}
      </h1>
    </header>

    <div v-if="articles.length">
      <section class="space-y-4">
        <article
          v-for="(article, index) in articles"
          :key="article.slug"
          class="flex bg-white border border-gray-300 rounded-md  dark:border-none hover:shadow-md dark:bg-gray-800"
        >
          <div
            v-if="article.img"
            class="w-1/2 bg-center bg-cover rounded-l-md"
            :style="'background-image: url(\'' + article.img + '\')'"
          />
          <div :class="article.img ? 'w-1/2' : ''">
            <header>
              <h2
                class="px-4 pt-3 pb-2 text-xl font-bold  dark:text-white dark:hover:text-gray-300"
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
            <div class="flex items-end px-4 pb-2 space-x-6 text-sm">
              <span class="dark:text-gray-400">{{
                formatDate(article.updatedAt)
              }}</span>
              <span class="dark:text-gray-400">
                {{ article.readingStats.text }}
              </span>
            </div>
          </div>
        </article>
      </section>
    </div>

    <div v-else>
      <p class="dark:text-gray-300">Nothing was found</p>
    </div>
  </section>
</template>

<script>
export default {
  // _slug.vue script
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
  async asyncData({ $content, params }) {
    // get the articles where the current tag is included in
    // their tag front matter data and their status is published.
    const slug = params.slug;

    const articles = await $content("articles")
      .where({
        tags: { $contains: slug },
        status: "published",
      })
      .fetch();

    return {
      articles,
      slug,
    };
  },
};
</script>
