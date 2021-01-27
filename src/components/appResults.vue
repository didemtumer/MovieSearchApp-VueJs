<template>
  <div class="container">
    <div class="results">
      <div class="card" v-for="item in movies" :key="item">
        <img :src="item.Poster" class="card-img-top" :alt="item.Title" />
        <div class="card-body">
          <h5 class="card-title">{{ item.Title }}</h5>
          <small>{{ item.Year }} / {{ item.Type }} </small>
        </div>
        <div class="favorite">
          <a href="#" @click="$emit('sendTofFav', item)" ><img src="../assets/favorite.svg" alt="" /></a>
          <button class="btn-sm btn-warning">IMDB</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["item", "movies"],
  emits: ["sendTofFav"]
};
</script>
<style>

</style>