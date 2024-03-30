<template>
      <!-- Link voor elk jaar -->
      <nav v-for="year in Object.keys(data)" >
        <NuxtLink :to="`/years/${year}`">{{ year }}</NuxtLink>
    </nav>
</template>

<script setup>

    const { data } = await useFetch('https://cssday.nl/data.json')
    // haal hiermee de slug op
    // const route = useRoute();
    // console.log(route.params.id)
</script>