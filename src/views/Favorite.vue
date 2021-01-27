<template>
  <div class="main_favorites results">
    <div class="card" v-for="item in favorites" :key="item">
      <img :src="item.Poster" class="card-img-top" :alt="item.Title" />
      <div class="card-body">
        <h5 class="card-title">{{ item.Title }}</h5>
        <small>{{ item.Year }} / {{ item.Type }} </small>
      </div>
      <div class="favorite">
        <button class="btn-sm btn-danger" @click="$emit('deleteTofFav', item)">
          DELETE
        </button>
        <button class="btn-sm btn-warning">IMDB</button>
      </div>
    </div>
  </div>
</template>


<script>
import axios from "axios";
export default {
  props: ["item"],
  emits: ["deleteTofFav"],
  created() {
    axios.get("http://localhost:3000/favorites").then((favorite_response) => {
      console.log("favorite_response", favorite_response);
      this.favorites = favorite_response.data;
    });
  },
};
</script>
