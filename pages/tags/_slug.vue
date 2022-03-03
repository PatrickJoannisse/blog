<template>
  <section>
    <header>
      <h1 class="text-5xl font-extrabold leading-loose">
        Post about #{{ slug }}
      </h1>
    </header>

    <div v-if="articles.length">{{ articles }}</div>

    <div v-else>Nothing was found</div>
  </section>
</template>

<script>
export default {
  layout: "BlogPost",
  // _slug.vue script
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
