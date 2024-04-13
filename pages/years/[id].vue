<template>
    <section class="year-intro">
        <NuxtLink :to="data[$route.params.id].link" :class="data[$route.params.id].color.name"><h1>{{ data[$route.params.id].title }}</h1></NuxtLink>
        <p v-for="day in data[$route.params.id].date">{{ day }}</p>
        <p>Venue: {{ data[$route.params.id].venue }}</p>
        <p v-if="data[$route.params.id].mc" v-for="mc in data[$route.params.id].mc">MC: {{ mc.name }}</p>
    </section>
    

    <!-- speaker carousel -->
    <h2>Speakers</h2>
    <section class="speaker-carousel">
        <button  v-for="speaker in data[$route.params.id].speakers" :popovertarget="speaker.name">
            <h3>{{ speaker.name }}</h3>
            
            <img v-if="speaker.avatar" :src="speaker.avatar" :alt="speaker.name" width="200" height="200">
            <img v-else src="/public/css-day.png" alt="no-avatar" width="200" height="200">

            <p v-if="speaker.talk.title">{{ speaker.talk.title }}</p>
        </button>
    </section>

    <!-- popover -->
    <section class="popover" v-for="speaker in data[$route.params.id].speakers" :id="speaker.name" popover="auto">
        <section class="popover-close-button-container">
            <button :popovertarget="speaker.name" popovertargetaction="hide">
                <span aria-hidden=”true”>&#10540;</span>
                <span>Close</span>
            </button>
        </section>
       
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
        height:92%;
        background-color: var(--thistle);
        border-radius:1rem;
        border:none;
    }
    .popover h3, .popover p, .popover a{
        margin-left: 1rem;
        margin-right: 1rem;
    }
    .popover-description{
        height:15rem;
        overflow:scroll;
        background-color: var(--pale-purple);
    }
    .popover-close-button-container{
        width:100%;
        display:flex;
        justify-content: end;
    }
    .popover button{
        border-radius: 1rem;
        padding:.5rem 1rem;
        background-color: var(--prussian-blue);
        color: white;
        font-size:1.5rem;
        border:none;
        margin:1rem;
    }
    a{
        display:block;
    }
    .popover a{
        color:darkslategray;
        text-decoration-color: var(--prussian-blue);
    }

    /* colors */
    .red{
        color: #ff0000;
        -webkit-text-stroke: .01px white;
    }
    .navy{
        color: #000080;
        -webkit-text-stroke: .01px white;
    }
    .olivedrab{
        color: #6b8e23;
        -webkit-text-stroke: .01px white;
    }
    .hotpink{
        color: #ff69b4;
        -webkit-text-stroke: .01px white;
    }
    .goldenrod{
        color: #daa520;
        -webkit-text-stroke: .01px white;
    }
    .tomato{
        color: #ff6347;
        -webkit-text-stroke: .01px white;
    }
    .deepskyblue{
        color: #00bfff;
        -webkit-text-stroke: .01px white;
    }
    .mediumseagreen{
        color: #3cb371;
        -webkit-text-stroke: .01px white;
    }
    .darkorchid{
        color: #9932cc;
        -webkit-text-stroke: .01px white;
    }
    .peru{
        color: #cd853f;
        -webkit-text-stroke: .01px white;
    }
</style>