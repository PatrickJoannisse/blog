<template>
  <section>
    <header class="max-w-screen-lg mx-auto px-4 py-4">
      <h1 class="text-5xl font-extrabold dark:text-gray-100">
        {{ article.title }}
      </h1>
      <div class="text-sm my-4 flex items-center space-x-6">
        <span class="dark:text-gray-400">{{
          formatDate(article.updatedAt)
        }}</span>
        <p class="sr-only">Tags:</p>
        <ul class="inline-flex space-x-2 my-2">
          <li v-for="tag in article.tags" :key="tag">
            <NuxtLink
              :to="`/tags/${tag}/`"
              class="
                inline-flex
                items-center
                px-2.5
                py-0.5
                rounded-md
                font-medium
                bg-[#3f37c9]
                hover:bg-[#4361ee]
                text-white
                transition
                duration-150
              "
              >#{{ tag }}</NuxtLink
            >
          </li>
        </ul>
      </div>
    </header>

    <img
      v-if="article.img"
      :src="article.img"
      :alt="article.alt"
      class="max-w-screen-xl mx-auto"
    />
    <p class="max-w-screen-xl mx-auto dark:text-gray-600 text-right italic">
      {{ article.alt }}
    </p>
    <article
      class="
        prose
        lg:prose-lg
        dark:prose-invert
        dark:prose-a:text-indigo-400
        dark:hover:prose-a:text-indigo-500
        prose-a:transition prose-a:duration-150
        max-w-screen-lg
        mx-auto
        mt-6
      "
    >
      <p class="lead">{{ article.description }}</p>
      <nuxt-content :document="article" />
    </article>
  </section>
</template>

<script>
export default {
  layout: "BlogPost",
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug)
      .where({
        status: "published",
      })
      .fetch();
    return { article };
  },
  methods: {
    formatDate(date) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(date).toLocaleDateString("en", options);
    },
  },
  head() {
    return {
      title: this.article.title,
    };
  },
};
</script>
