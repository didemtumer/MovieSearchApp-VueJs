<template>
  <div class="container">
    <div class="search-bar">
      <input
        class="form-control"
        type="text"
        placeholder="What u looking for?"
        aria-label="Search"
        v-model="movie"
        @keydown.enter.prevent="$emit('movieSearch', movie)"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["movie"],
};
</script>
