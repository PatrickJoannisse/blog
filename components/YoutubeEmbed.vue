<template>
  <iframe
    class="w-full aspect-video"
    :src="url"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  ></iframe>
</template>

<script>
export default {
  name: "YouTubeEmbed",
  props: {
    url: String,
  },
};
</script>
