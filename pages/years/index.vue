<template>
    <ul class="ul-styling-buttons">
        <li class="li-styling-buttons" v-for="year in Object.keys(data)" >
            <AtomsButtonLink :year="year" class="link-style-buttons"/>
        </li>
    </ul>
</template>

<script setup>
    const { data } = await useFetch('https://cssday.nl/data.json')
</script>

<style scoped>
ul{
    padding:0;
    list-style: none;
    display:grid;
    grid-template-columns: repeat(2, calc(50% - .5rem));
    grid-gap: 0 1rem;
}



</style>