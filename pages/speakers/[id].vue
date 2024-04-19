<template>
<div v-for="dataObject in data">
    <!-- $route.params.id hiermee haal je data uit de slug op -->
    <h1 v-if="dataObject.name === $route.params.id">{{ dataObject.name }}</h1>

    <!-- deze code haalt alle data op die in het object staan waarbij de naam waarde overeenkomt met de waarde uit de slug -->
    <div v-if="dataObject.name === $route.params.id">
        <img :src="dataObject.avatar">
        <!-- <p :v-for="datee in dataObject.edition.date">{{ datee }}</p> -->
        <p>{{ dataObject.venue }}</p>
        <p>{{ dataObject.talk.title }}</p>
        <p>{{ dataObject.talk.description }}</p>

      <div v-for="(value, key) in dataObject">
        {{ key }}: {{ value }}
      </div>
    </div>

</div>
    <!-- <pre>{{ data }}</pre> -->
    <!-- <pre>
    {{ carmenData }}
  </pre> -->
</template>

<script setup>

    const { data } = await useFetch('https://cssday.nl/data/speakers.json')




//     onMounted( () =>{
//   // Zoekmethode om het object van Carmen Ansio op te halen
//   function findCarmen(data) {
//   for (let item of data) {
//     if (item.name === "Carmen Ansio") {
//       return item;
//     }
//   }
//   return null; // Als Carmen niet wordt gevonden
// }
//     })
  
   


// Carmen Ansio's gegevens
// const carmenData = findCarmen(apiData);
// if (carmenData) {
//   console.log(carmenData);
// } else {
//   console.log("Carmen Ansio niet gevonden.");
// }



    // const speakerData = speakersData.find(speaker => speaker.slug === $route.params.id)
    console.log(data)
    // haal hiermee de slug op
    // const route = useRoute();
    // console.log(route.params.id)
</script>