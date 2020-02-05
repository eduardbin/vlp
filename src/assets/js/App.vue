<template>
  <div id="app">
    <h1 class="text-center">Усі видання</h1>
    <div class="row align-center">
      <div
        class="column small-12 medium-6 large-3"
        v-for="(book, index) in products"
        v-if
      >
        <article class="ba-product">
          <a :href="book.url">
            <img :src="book.img" :alt="book.title" />
          </a>
          <h3 class="ba-product__title">{{ book.title }}</h3>

          <p class="ba-product__author">{{ book.authors }}</p>

          <div class="ba-price">{{ book.price }}</div>
        </article>
        <!-- /.ba-product -->
      </div>
      <!-- /.column small-12 medium-6 large-3 -->
    </div>
    <!-- /.row -->
    <div class="column small-12 medium-10">
      <Pagination />
      <hr />
    </div>
    <!-- /.column small-12 medium-10 -->
  </div>
</template>

<script>
import json from "../db/data.json";

import Pagination from "./components/Pagination.vue";

export default {
  data() {
    return {
      itemsPerPage: 2,
      products: json
    };

    components: {
      Pagination;
    }
  }
};
</script>
