<template>
    <section v-for="dataObject in data">
        <h1 v-if="dataObject.title === $route.params.id">{{ dataObject.title }}</h1>

        <section class="info-section" v-if="dataObject.title === $route.params.id">
            <section v-for="item in dataObject.speaker">
                <img v-if="item.avatar" :src="item.avatar">
                <p>Speaker: {{ item.name }}</p>
            </section>

            <!-- date of CSS days attended-->
            <p>Date:</p>
            <p class="dates" v-if="Array.isArray(dataObject.edition.date)" v-for="date in dataObject.edition.date">{{ date }}</p>
            <p class="dates" v-else>{{ dataObject.edition.date }}</p>

            <!-- location -->
            <p>Venue: {{ dataObject.edition.venue }}</p>

            <!-- presentation description -->
            <p v-if="dataObject.description">{{ dataObject.description }}</p>
            
            <!-- presentation slides & video -->
            <a class="speaker-links" v-if="dataObject.slides" href="dataObject.slides">Presentation slides</a>
            <a class="speaker-links" v-if="dataObject.video['youtube-link']" :href="dataObject.video['youtube-link']" target="_blank">Presentation Video</a>
        </section>

    </section>
</template>
    
<script setup>
    const { data } = await useFetch('https://cssday.nl/data/talks.json')
</script>

<style scoped>
    h1{
        margin-left:1rem;
    }
    img{
        border-radius:1rem;
    }
</style>