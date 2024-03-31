<template>
    <ul>
        <li v-for="year in Object.keys(data)" >
            <AtomsButtonLink :year="year" />
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
    grid-gap:1rem;
    margin:1rem;
}
li{
    padding: 2rem;
    display: flex;
    justify-content: center;
    border-radius:1rem;
    font-size:1.5rem;
}
li:nth-child(5n){
    background-color: var(--pale-purple);
}
li:nth-child(5n+1){
    background-color: var(--thistle);
}
li:nth-child(5n+2){
    background-color: var(--pomp-and-power);
}
li:nth-child(5n+3){
    background-color: var(--tekhelet);
}
li:nth-child(5n+4){
    background-color: var(--prussian-blue);
}
li:nth-child(5n+3) a, li:nth-child(5n+4) a, li:nth-child(5n+2) a{
    color:white;
}



</style>