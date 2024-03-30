<template>
    <NuxtLink :to="`/years/${year}`">{{ year }}</NuxtLink>
</template>

<script setup>
    const{ year } = defineProps(["year"])
</script>

<style scoped>
a{
    color:black;
}
</style>