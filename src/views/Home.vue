<template>
  <div class="home">
    <banner img="/img/banner-river.svg" />
    <pagination />
  </div>
</template>

<script>
// @ is an alias to /src
import Banner from "@/components/Banner";
import Pagination from "@/components/Pagination";

export default {
  name: "Home",
  components: { Banner, Pagination },
};
</script>
