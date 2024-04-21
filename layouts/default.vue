<template>
    

    <nav>
        <NuxtLink to="/" class="css-day-homelink">CSS Day</NuxtLink>
        <ul>
            <NuxtLink to="/years">Years</NuxtLink>
            <NuxtLink to="/speakers">Speakers</NuxtLink>
            <NuxtLink to="/talks">Talks</NuxtLink>
        </ul>
    </nav>

    <slot />
</template>

<script setup>

</script>

<style>

    @import url('https://fonts.googleapis.com/css2?family=Black+Ops+One&display=swap');

    :root{
        --pale-purple: #E8D7F1;
        --thistle: #D3BCCC;
        --pomp-and-power: #A167A5;
        --tekhelet: #4A306D;
        --prussian-blue: #0E273C;
        --background-color: #0D0D0D;
    }
    html{
        font-family: "Black Ops One", system-ui;
        font-weight: 400;
        font-style: normal;  
        background-color: var(--background-color);
        color:white;
    }
    body{
        padding:0;
        margin:0;
    }
    nav{
        margin-top:1rem;
    }
    nav ul{
        padding:0;
    }
    nav a{
        color:white;
        margin: 1rem;
    }
    .css-day-homelink{
        margin:1rem;
        font-size:3rem;
    }
    .router-link-active {
        color:hotpink;
    }

    /* color button links styling */
    .ul-styling-buttons{
        padding:0;
        list-style: none;
        margin: 3rem 1rem 1rem;
    }
    .link-style-buttons{
        padding: 2rem;
        display: flex;
        justify-content: center;
        font-size:1.5rem;
    }
    .li-styling-buttons{
        border-radius:1rem;
        margin-bottom:1rem;
    }
    .li-styling-buttons:nth-child(5n){
        background-color: var(--pale-purple);
    }
    .li-styling-buttons:nth-child(5n+1){
        background-color: var(--thistle);
    }
    .li-styling-buttons:nth-child(5n+2){
        background-color: var(--pomp-and-power);
    }
    .li-styling-buttons:nth-child(5n+3){
        background-color: var(--tekhelet);
    }
    .li-styling-buttons:nth-child(5n+4){
        background-color: var(--prussian-blue);
    }
    .li-styling-buttons:nth-child(5n+3) a, .li-styling-buttons:nth-child(5n+4) a, .li-styling-buttons:nth-child(5n+2) a{
        color:white;
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
    .speaker-links{
        color:white;
        display: block;
    }
    .info-section{
        padding: 0 1rem;
        margin-bottom:3rem;
    }
    .info-section img{
        width:100%; 
    }
</style>