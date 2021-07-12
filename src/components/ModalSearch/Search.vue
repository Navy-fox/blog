<template>
  <div class="wrapper">
    <table-search :items="items" />
  </div>
</template>

<script>
import TableSearch from "@/components/ModalSearch/TableSearch";
import { SEARCH_TELECOM } from "@/data/SEARCH_TELECOM";
export default {
  name: "Search",
  components: { TableSearch },
  data() {
    return {
      items: SEARCH_TELECOM,
    };
  },
};
</script>

<style scoped></style>
