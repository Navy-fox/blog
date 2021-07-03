<template>
  <div class="home">
    <p class="title">This is our blog</p>
    <banner :banner="banners.top" />
    <news-line class="wrapper blog-margin" :news="posts.slice(0, 8)" />
    <banner class="blog-margin" :banner="banners.bottom" />
    <news-line class="wrapper blog-margin" :news="posts.slice(8)" />
    <pagination />
  </div>
</template>

<script>
// @ is an alias to /src
import Banner from "@/components/Banner";
import Pagination from "@/components/Pagination";
import NewsLine from "@/components/NewsLine";
import { POSTS } from "@/data/POSTS";
import { BANNERS } from "@/data/BANNERS";

export default {
  name: "Home",
  components: { NewsLine, Banner, Pagination },
  data() {
    return {
      posts: POSTS,
      banners: BANNERS,
    };
  },
};
</script>

<style lang="scss">
.blog-margin {
  margin-top: 120px;
}
.title {
  margin-top: 53px;
  margin-bottom: 88px;
  margin-left: 142px;
}
</style>
