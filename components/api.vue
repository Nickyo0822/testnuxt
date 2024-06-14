<template>
  <div class="allCats">
    <figure v-for="e in data" :key="item" class="cat">
      <img :src="'https://cataas.com/cat/'+e._id" alt="">
      <figcaption>{{ e._id }}</figcaption>
    </figure>
  </div>
</template>

<script setup lang="ts">
  const { data: data } = await useFetch('https://cataas.com/api/cats?tags=cute')
</script>

<style>
  .allCats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    width: 100%;
    gap: 2rem;
    padding: 1rem;
  }

  .cat img {
    width: 75%;
  }
</style>