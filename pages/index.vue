<template>
  <article-list :articles="articles"></article-list>
</template>

<script>
import ArticleList from "../components/ArticleList.vue";
export default {
  components: { ArticleList },
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
        "publishedAt",
        "readingStats",
      ])
      .sortBy("publishedAt", "desc")
      .fetch();

    return {
      articles,
    };
  },
  head: {
    meta: [
      {
        hid: "description",
        name: "description",
        content: "Hi, I'm Patrick Joannisse and this is my little blog.",
      },
    ],
  },
};
</script>
