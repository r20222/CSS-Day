<template>
<section v-for="dataObject in data">
    <!-- $route.params.id hiermee haal je data uit de slug op -->
    <h1 v-if="dataObject.name === $route.params.id">{{ dataObject.name }}</h1>

    <!-- deze code haalt alle data op die in het object staan waarbij de naam waarde overeenkomt met de waarde uit de slug -->
    <section class="speaker-section" v-if="dataObject.name === $route.params.id">
        <!-- speaker avatar -->
        <img alt="" :src="dataObject.avatar">

        <!-- date of CSS days attended-->
        <p>Date:</p>
        <p class="dates" v-if="Array.isArray(dataObject.edition.date)" v-for="date in dataObject.edition.date">{{ date }}</p>
        <p class="dates" v-else>{{ dataObject.edition.date }}</p>

        <!-- venue of CSS days -->
        <p>Venue: {{ dataObject.edition.venue }}</p>

        <!-- title & description of presentation -->
        <p v-if="dataObject.talk.title">{{ dataObject.talk.title }}</p>
        <p v-if="dataObject.talk.description">{{ dataObject.talk.description }}</p>

        <!-- link to slides & youtube presentation video -->
        <a class="speaker-links" v-if="dataObject.talk.slides" :href="dataObject.talk.slides" target="_blank">Slides of the presentation</a>
        <a class="speaker-links" v-if="dataObject.talk.video['youtube-link']" :href="dataObject.talk.video['youtube-link']" target="_blank">Presentation Video</a>
    </section>
  </section>
</template>

<script setup>
    const { data } = await useFetch('https://cssday.nl/data/speakers.json')
</script>

<style scoped>
h1{
  margin:2rem 1rem .5rem;
}
.dates{
  line-height: 0;
}
.speaker-links{
  color:hotpink;
  display: block;
}
.speaker-section{
  padding: 0 1rem;
  margin-bottom:3rem;
}
.speaker-section img{
  width:100%;
}
</style>