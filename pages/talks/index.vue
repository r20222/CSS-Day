<template>
  <ul class="ul-styling-buttons">
    <li class="li-styling-buttons" v-for="talk in data">
      <NuxtLink v-if="talk.title" :to="`/talks/${talk.title}`" class="link-style-buttons">{{ talk.title }}</NuxtLink>
    </li>
  </ul>
</template>

<script setup>
  const { data } = await useFetch('https://cssday.nl/data/talks.json')
</script>

<style scoped>
a{
  display: flex;
  justify-content: start;
}
</style>