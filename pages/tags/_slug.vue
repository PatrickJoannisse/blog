<template>
  <section>
    <header>
      <h1 class="text-4xl font-extrabold leading-loose dark:text-white">
        Posts about #{{ slug }}
      </h1>
    </header>

    <article-list :articles="articles"></article-list>
  </section>
</template>

<script>
import ArticleList from "../../components/ArticleList.vue";
export default {
  components: { ArticleList },
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
