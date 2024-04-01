<template>
    <section class="year-intro">
        <NuxtLink :to="data[$route.params.id].link"><h1>{{ data[$route.params.id].title }}</h1></NuxtLink>
        <p v-for="day in data[$route.params.id].date">{{ day }}</p>
        <p>Venue: {{ data[$route.params.id].venue }}</p>
        <p v-if="data[$route.params.id].mc" v-for="mc in data[$route.params.id].mc">MC: {{ mc.name }}</p>
    </section>
    

    <!-- speaker carousel -->
    <h2>Speakers</h2>
    <section class="speaker-carousel" :class="data[$route.params.id].color.name">
        <button  v-for="speaker in data[$route.params.id].speakers" :popovertarget="speaker.name">
            <h3>{{ speaker.name }}</h3>
            
            <img v-if="speaker.avatar" :src="speaker.avatar" :alt="speaker.name" width="200" height="200">
            <img v-else src="/public/css-day.png" alt="no-avatar" width="200" height="200">

            <p v-if="speaker.talk.title">{{ speaker.talk.title }}</p>
        </button>
    </section>

    <!-- popover -->
    <section class="popover" v-for="speaker in data[$route.params.id].speakers" :id="speaker.name" popover="auto">
        <button :popovertarget="speaker.name" popovertargetaction="hide">
            <span aria-hidden=”true”>❌</span>
            <span>Close</span>
        </button>
        <h3>{{speaker.name}}</h3>
        <p v-if="speaker.country">{{  speaker.country }}</p>
        <p>{{ speaker.talk.title }}</p>
        <NuxtLink v-if="speaker.talk.slides" :to="speaker.talk.slides" target="_blank">Presentation slides</NuxtLink>
        <NuxtLink v-if="speaker.talk.video['youtube-link']" :to="speaker.talk.video['youtube-link']" target="_blank">Presentation Video</NuxtLink>
        <p class="popover-description" v-if="speaker.talk.description">{{ speaker.talk.description }}</p>
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
        padding-top:2rem;
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
    h3{
        height:46.4px
    }
    .popover{
        margin:1rem;
        width:calc(100% - 3rem);
    }
    .popover-description{
        height:15rem;
        overflow:scroll;
    }
    a{
        display:block;
    }

    /* colors */
    .red{
        background-color: #ff0000;
    }
    .navy{
        background-color: #000080;
    }
    .olivedrab{
        background-color: #6b8e23;
    }
    .hotpink{
        background-color: #ff69b4;
    }
    .goldenrod{
        background-color: #daa520;
    }
    .tomato{
        background-color: #ff6347;
    }
    .deepskyblue{
        background-color: #00bfff;
    }
    .mediumseagreen{
        background-color: #3cb371;
    }
    .darkorchid{
        background-color: #9932cc;
    }
    .peru{
        background-color: #cd853f;
    }
</style>