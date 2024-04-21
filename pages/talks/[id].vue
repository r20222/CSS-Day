<template>
    <section v-for="dataObject in data">
        <h1 v-if="dataObject.title === $route.params.id" :class="dataObject.edition.color.name">{{ dataObject.title }}</h1>

        <section class="info-section" v-if="dataObject.title === $route.params.id">
            <section v-for="item in dataObject.speaker">
                <img v-if="item.avatar" :src="item.avatar">
                <h2 :class="dataObject.edition.color.name">Speaker:</h2> 
                <p>{{ item.name }}</p>
            </section>

            <!-- date of CSS days attended-->
            <section>
                <h2 :class="dataObject.edition.color.name">Date:</h2>
                <p class="dates" v-if="Array.isArray(dataObject.edition.date)" v-for="date in dataObject.edition.date">{{ date }}</p>
                <p class="dates" v-else>{{ dataObject.edition.date }}</p>
            </section>
            

            <!-- location -->
            <section>
                <h2 :class="dataObject.edition.color.name">Venue:</h2>
                <p>{{ dataObject.edition.venue }}</p>
            </section>
          

            <!-- presentation description -->
            <p class="title-description" v-if="dataObject.description">{{ dataObject.description }}</p>
            
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
    
    .info-section section{
        margin-top:2rem;
    }
    .info-section section p, .info-section section a{
        line-height: 0;
    }
    .title-description{
        margin-top:4rem;
    }
</style>