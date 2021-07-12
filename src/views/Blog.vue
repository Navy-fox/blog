<template>
  <div class="blog">
    <blog-title />
    <banner hidden-text :banner="banners.top" />
    <div class="blog__text">
      <p>
        During the last day, the task was to work on the tricky bits, very
        difficult conversations.
      </p>
      <ul class="blog__list">
        <li>
          We went through how to de-escalate issues and work with customers to
          help alleviate problems
        </li>
        <li>
          We also ran through role playing interactions on what we learnt to
          make sure we knew how to use the experience from the training we
          received in the real world.
        </li>
      </ul>
      <p>
        Revoluters that participated in this training said they would put these
        skills into practice by applying ‘more active listening’ and they called
        it 'mind-changing'.
      </p>
      <p>
        This month one of our Vulnerable Customers champions in our support team
        demonstrated some of the skills learnt during the workshop to help a
        vulnerable customer who was feeling shocked, scared, unprotected and was
        dealing with negative thoughts. Our support agent spent time on the
        phone with the customer and calmly applied some recently learned
        techniques to help resolve the issue. We followed up with this customer
        a couple of days later to ensure that they were feeling better and
        checked if we could do anything to provide further support.
      </p>
    </div>
    <tags :tags="tags" />
    <p class="tags-title">Also:</p>
    <news-line class="wrapper blog-margin" :news="posts.slice(0, 3)" />
  </div>
</template>

<script>
import NewsLine from "@/components/global/NewsLine";
import { POSTS } from "@/data/POSTS";
import { BANNERS } from "@/data/BANNERS";
import Banner from "@/components/global/Banner";
import BlogTitle from "@/components/Blog/BlogTitle";
import Tags from "@/components/Tags";
import { TAGS } from "@/data/TAGS";
export default {
  name: "Blog",
  components: { Tags, BlogTitle, Banner, NewsLine },
  data() {
    return {
      posts: POSTS,
      banners: BANNERS,
      tags: TAGS,
    };
  },
};
</script>

<style lang="scss">
.blog {
  margin-bottom: 120px;
  &__text {
    font-family: $font, sans-serif;
    font-size: 28px;
    line-height: 170%;
    color: $font-color-dark;
    display: flex;
    flex-direction: column;
    gap: 48px;
    margin: 120px 40% 120px 142px;
    @media (max-width: $screen-laptop) {
      gap: 34px;
      font-size: 20px;
      margin-top: 96px;
      margin-bottom: 96px;
      margin-right: 35%;
    }
    @media (max-width: $screen-square) {
      margin-left: 96px;
      margin-right: 20%;
    }
    @media (max-width: $screen-tablet) {
      margin: 48px 72px;
    }
    @media (max-width: $screen-mobile) {
      font-size: 16px;
      line-height: 130%;
      margin: 24px 32px;
      gap: 21px;
    }
  }

  &__list {
    list-style-type: decimal;
    padding-left: 35px;
    @media (max-width: $screen-mobile) {
      list-style-type: disc;
    }
  }
  .tags-title {
    margin-top: 120px;
    margin-left: 142px;
    @media (max-width: $screen-laptop) {
      margin-top: 96px;
    }
    @media (max-width: $screen-square) {
      margin-left: 24px;
    }
    @media (max-width: $screen-mobile) {
      margin-top: 32px;
      margin-left: 24px;
    }
  }
}
</style>
