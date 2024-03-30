<template>
    <p>{{ $route.params.id }}</p>
    <!-- <pre>{{ data[$route.params.id] }}</pre> -->

</template>

<script setup>

    const { data } = await useFetch('https://cssday.nl/data/speakers.json')
    // haal hiermee de slug op
    // const route = useRoute();
    // console.log(route.params.id)
</script>