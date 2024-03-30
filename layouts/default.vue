<template>
    <h1>holaaa</h1>

    <!-- Link voor elk jaar -->
    <nav v-for="year in Object.keys(data)">
        <NuxtLink :to="`/years/${year}`">{{ year }}</NuxtLink>
    </nav>
    <slot />
</template>

<script setup>
    const { data } = await useFetch('https://cssday.nl/data.json')
</script>