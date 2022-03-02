<template>
  <section>
    <header>
      <h1 class="text-5xl font-extrabold leading-loose">{{ article.title }}</h1>
      <p class="mb-4">{{ article.description }}</p>
    </header>

    <div class="text-sm mb-4 flex items-center space-x-6">
      <span>{{ formatDate(article.updatedAt) }}</span>
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
              text-sm
              font-medium
              bg-gray-100
              text-gray-800
            "
            >#{{ tag }}</NuxtLink
          >
        </li>
      </ul>
    </div>
    <img :src="article.img" :alt="article.alt" />
    <article class="prose lg:prose-lg max-w-none">
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
