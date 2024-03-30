<template>
    <h1>hello</h1>
    <!-- yaartallen ophalen -->
    <!-- <pre v-for="year in Object.keys(data)">{{ year }}</pre> -->


    <!-- Link voor elk jaar -->
    <!-- <nav v-for="year in Object.keys(data)">
        <NuxtLink :to="'/years/' + year">{{ year }}</NuxtLink>
    </nav> -->
    <!-- <pre>{{ data["2013"] }}</pre> -->
    <!-- <section v-for="year in Object.keys(data)" :key="year">
        <NuxtLink :to="`/${data[year].date[0]}`">{{ data[year].title }}</NuxtLink>
    </section> -->
</template>

<script setup>
    // const { data } = await useFetch('https://cssday.nl/data.json')
    
    // ik wil heel graag voor elke data een details pagina maken met alle inhoud van dat jaar.
    // het lukt nog niet echt om het jaartal uit de date te halen.
</script>

<style>
</style>