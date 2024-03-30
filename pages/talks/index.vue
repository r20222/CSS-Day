<template>
    <nav v-for="talk in data">
      <NuxtLink :to="`/speakers/${talk}`">{{ talk.title }}</NuxtLink>
    </nav>
</template>

<script setup>

  const { data } = await useFetch('https://cssday.nl/data/talks.json')
  // haal hiermee de slug op
  // const route = useRoute();
  // console.log(route.params.id)
</script>