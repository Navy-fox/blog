<template>
  <div class="preview">
    <preview-title />
    <banner :banner="banners.top" />
    <news-line class="wrapper blog-margin" :news="posts.slice(0, 6)" />
  </div>
</template>

<script>
import Banner from "@/components/Banner";
import NewsLine from "@/components/NewsLine";
import PreviewTitle from "@/components/PreviewTitle";
import { POSTS } from "@/data/POSTS";
import { BANNERS } from "@/data/BANNERS";

export default {
  name: "Preview",
  components: { Banner, NewsLine, PreviewTitle },
  data() {
    return {
      posts: POSTS,
      banners: BANNERS,
    };
  },
};
</script>
