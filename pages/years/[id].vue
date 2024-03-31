<template>
    <section class="year-intro">
        <h1>{{ $route.params.id }}</h1>
        <NuxtLink :to="data[$route.params.id].link">{{ data[$route.params.id].title }}</NuxtLink>
        <p v-for="day in data[$route.params.id].date">{{ day }}</p>
        <p>{{ data[$route.params.id].venue }}</p>
    </section>
    

    <!-- speaker carousel -->
    <h2>Speakers</h2>
    <section class="speaker-carousel">
        <section  v-for="speaker in data[$route.params.id].speakers">
            <h3>{{ speaker.name }}</h3>
            <img :src="speaker.avatar">
            <p>{{ speaker.talk.title }}</p>
        </section>
    </section>


</template>

<script setup>

    const { data } = await useFetch('https://cssday.nl/data.json')
    // haal hiermee de slug op
    // const route = useRoute();
    // console.log(route.params.id)
</script>
<style scoped>
    .year-intro{
        margin:1rem;
    }
    /* speaker carousel */
    .speaker-carousel{
        display: flex;
        overflow-x:scroll;
    }
    .speaker-carousel img{
        border-radius: 1rem;
    }
    .speaker-carousel section{
        margin-right:1rem;
    }
    h2, .speaker-carousel{
        margin-left:1rem;
    }

</style>