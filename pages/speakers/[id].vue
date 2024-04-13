<template>
    <p>{{ $route.params.id }}</p>
<div v-for="dataObject in data">
    <h1 v-if="dataObject.name === $route.params.id">{{ dataObject.name }}</h1>
</div>
    <!-- <pre>{{ data[$route.params.id] }}</pre> -->
    <pre>
    {{ carmenData }}
  </pre>
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