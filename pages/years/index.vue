<template>
    <ul v-for="year in Object.keys(data)" >
        <li>
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
}
ul:nth-child(5n){
    background-color: var(--pale-purple);
}
ul:nth-child(5n+1){
    background-color: var(--thistle);
}
ul:nth-child(5n+2){
    background-color: var(--pomp-and-power);
}
ul:nth-child(5n+3){
    background-color: var(--tekhelet);
}
ul:nth-child(5n+4){
    background-color: var(--prussian-blue);
}
ul:nth-child(5n+4) li a{

    color:white;
}

</style>