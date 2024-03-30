<template>
    <NuxtLink to="/">CSS DAY</NuxtLink>

    <ul>
        <NuxtLink to="/years">Years</NuxtLink>
        <NuxtLink to="/speakers">Speakers</NuxtLink>
        <NuxtLink to="/talks">Talks</NuxtLink>
    </ul>
  
    <slot />
</template>

<script setup>

</script>

<style>
    :root{
        --pale-purple: #E8D7F1;
        --thistle: #D3BCCC;
        --pomp-and-power: #A167A5;
        --tekhelet: #4A306D;
        --prussian-blue: #0E273C;
    }
</style>