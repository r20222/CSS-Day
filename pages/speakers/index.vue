<template>
  <div>
    <nav v-for="speaker in data">
      <NuxtLink :to="`/speakers/${speaker}`">{{ speaker.name }}</NuxtLink>
    </nav>
  </div> 
</template>

<script setup>

  const { data } = await useFetch('https://cssday.nl/data/speakers.json')
  // haal hiermee de slug op
  // const route = useRoute();
  // console.log(route.params.id)
</script>