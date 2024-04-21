<template>
    <section class="year-intro">
        <NuxtLink :to="data[$route.params.id].link" :class="data[$route.params.id].color.name" target="_blank"><h1>{{ data[$route.params.id].title }}</h1></NuxtLink>
        <p v-for="day in data[$route.params.id].date">{{ day }}</p>
        <p>Venue: {{ data[$route.params.id].venue }}</p>
        <p v-if="data[$route.params.id].mc" v-for="mc in data[$route.params.id].mc">MC: {{ mc.name }}</p>
    </section>
    

    <!-- speaker carousel -->
    <h2>Speakers</h2>
    <section class="speaker-carousel">
        <button  v-for="speaker in data[$route.params.id].speakers">
            <NuxtLink :to="`/speakers/${speaker.name}`" class="carousel-link">{{ speaker.name }}</NuxtLink>
            
            <img v-if="speaker.avatar" :src="speaker.avatar" :alt="speaker.name" width="200" height="200">
            <img v-else src="/public/css-day.png" alt="no-avatar" width="200" height="200">

            <NuxtLink :to="`/talks/${speaker.talk.title}`" v-if="speaker.talk.title" class="carousel-link">{{ speaker.talk.title }}</NuxtLink>
        </button>
    </section>

</template>

<script setup>
    const { data } = await useFetch('https://cssday.nl/data.json')
</script>

<style scoped>
    .year-intro{
        margin:1rem;
        margin-top: 3rem;
    }
    .year-intro p{
        margin:0;
    }
    /* speaker carousel */
    .speaker-carousel{ 
        display: flex;
        overflow-x:scroll;
        padding-left:1rem;
        padding-bottom:2rem;
    }
    .speaker-carousel img{
        border-radius: 1rem;
    }
    .speaker-carousel button{
        margin-right:1rem;
        font-family: "Black Ops One", system-ui;
        display: flex;
        flex-direction: column;
        border:none;
        border-radius:1rem;
    }
    h2{
        margin-top:3rem;
        margin-left:1rem;
    }
    .carousel-link{
        font-size:1rem;
        text-align: left;
        margin: 1rem 0;
        color:black;
        text-decoration: underline hotpink;
    }
</style>