<template>
    <NuxtLink to="/" class="css-day-homelink">CSS DAY</NuxtLink>

    <nav>
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
    }
    html{
        font-family: "Black Ops One", system-ui;
        font-weight: 400;
        font-style: normal;  
       
    }
    body{
        padding:0;
        margin:0;
    }
    nav ul{
        padding:0;
    }
    nav a{
        color:black;
        margin: 1rem;
    }
    .css-day-homelink{
        margin:1rem;
    }
    .router-link-active {
        color:hotpink;
    }
   

</style>