<template>
    <section v-for="dataObject in data">
        <h1 v-if="dataObject.title === $route.params.id">{{ dataObject.title }}</h1>

        <section class="speaker-section" v-if="dataObject.title === $route.params.id">
            <h2 v-for="speaker in dataObject.speaker">Speaker: {{ dataObject.speaker.name }}</h2>
        </section>

    </section>
    <pre>{{ data }}</pre>
</template>
    
<script setup>
    const { data } = await useFetch('https://cssday.nl/data/talks.json')
</script>

<style scoped>

</style>