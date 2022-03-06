<template>
  <section>
    <header class="max-w-screen-lg px-4 py-4 mx-auto">
      <h1 class="text-3xl font-extrabold md:text-5xl dark:text-gray-100">
        {{ article.title }}
      </h1>
      <div class="flex items-center my-4 space-x-6 text-sm">
        <span class="dark:text-gray-400">{{
          formatDate(article.updatedAt)
        }}</span>
        <span class="dark:text-gray-400">
          {{ article.readingStats.text }}
        </span>
        <p class="sr-only">Tags:</p>
        <ul class="inline-flex my-2 space-x-2">
          <li v-for="tag in article.tags" :key="tag">
            <NuxtLink :to="`/tags/${tag}/`"
              ><tag>#{{ tag }}</tag></NuxtLink
            >
          </li>
        </ul>
      </div>
    </header>

    <img
      v-if="article.img"
      :src="article.img"
      :alt="article.alt"
      class="mx-auto xl:max-w-screen-xl"
    />
    <p
      v-if="article.alt"
      class="max-w-screen-xl mx-auto mt-1 mb-6 italic text-center text-gray-600"
    >
      {{ article.alt }}
    </p>
    <article
      class="max-w-screen-lg px-4 mx-auto prose  md:prose-md lg:prose-lg dark:prose-invert dark:prose-a:text-indigo-400 dark:hover:prose-a:text-indigo-500 prose-a:transition prose-a:duration-150"
    >
      <p class="lead">{{ article.description }}</p>
      <nuxt-content :document="article" />
    </article>
    <div class="max-w-screen-lg px-4 mx-auto my-6" id="content">
      <AuthorCard />
      <prev-next :prev="prev" :next="next" />
    </div>
  </section>
</template>

<script>
import PrevNext from "../../components/PrevNext.vue";
export default {
  components: { PrevNext },
  layout: "BlogPost",
  async asyncData({ $content, params }) {
    const article = await $content("articles", params.slug)
      .where({
        status: "published",
      })
      .fetch();
    const [prev, next] = await $content("articles")
      .where({
        status: "published",
      })
      .only(["title", "slug"])
      .sortBy("createdAt", "asc")
      .surround(params.slug)
      .fetch();
    return { article, prev, next };
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
