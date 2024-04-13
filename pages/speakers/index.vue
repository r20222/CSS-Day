<template>
  <ul class="ul-styling-buttons">
    <li class="li-styling-buttons" v-for="speaker in data">
      <NuxtLink :to="`/speakers/${speaker.name}`"  class="link-style-buttons">{{ speaker.name }}</NuxtLink>
    </li>
  </ul> 
</template>

<script setup>
  const { data } = await useFetch('https://cssday.nl/data/speakers.json')
</script>

<style scoped>
a{
  display: flex;
  justify-content: start;
}
</style>