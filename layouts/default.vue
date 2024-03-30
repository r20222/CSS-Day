<template>
    <h1>CSS DAY</h1>

    <ul>
        <NuxtLink to="/years">Years</NuxtLink>
        <NuxtLink to="/speakers">Speakers</NuxtLink>
        <NuxtLink to="/talks">Talks</NuxtLink>
    </ul>
  
    <slot />
</template>

<script setup>
    const { data } = await useFetch('https://cssday.nl/data.json')
</script>