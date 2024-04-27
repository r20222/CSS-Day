<template>
  <section class="year-intro">
    <NuxtLink
      :to="data[$route.params.id].link"
      :class="data[$route.params.id].color.name"
      target="_blank"
      ><h1>{{ data[$route.params.id].title }}</h1></NuxtLink
    >
    <p v-for="day in data[$route.params.id].date">{{ day }}</p>
    <p>Venue: {{ data[$route.params.id].venue }}</p>
    <p v-if="data[$route.params.id].mc" v-for="mc in data[$route.params.id].mc">
      MC: {{ mc.name }}
    </p>
  </section>

  <!-- speaker carousel -->
  <h2>Speakers</h2>
  <section class="speaker-carousel">
    <section
      class="carousel-card"
      v-for="speaker in data[$route.params.id].speakers"
    >
      <NuxtLink :to="`/speakers/${speaker.name}`" class="carousel-link">{{
        speaker.name
      }}</NuxtLink>

      <img
        v-if="speaker.avatar"
        :src="speaker.avatar"
        :alt="speaker.name"
        width="200"
        height="200"
      />
      <img
        v-else
        src="/public/css-day.png"
        alt="no-avatar"
        width="200"
        height="200"
      />

      <NuxtLink
        :to="`/talks/${speaker.talk.title}`"
        v-if="speaker.talk.title"
        class="carousel-link"
        >{{ speaker.talk.title }}</NuxtLink
      >
    </section>
  </section>
</template>

<script setup>
const { data } = await useFetch("https://cssday.nl/data.json");
</script>

<style scoped>
.year-intro {
  margin: 1rem;
  margin-top: 3rem;
}
.year-intro p {
  max-width: 70rem;
  margin: auto;
}

/* speaker carousel */
.speaker-carousel {
  display: flex;
  overflow-x: scroll;
  padding-left: 1rem;
  padding-bottom: 2rem;
}
.speaker-carousel img {
  border-radius: 1rem;
}
.carousel-card {
  background-color: rgb(252, 250, 250);
  margin: 1rem 1rem 1rem 0;
  font-family: "Black Ops One", system-ui;
  display: flex;
  flex-direction: column;
  border: none;
  border-radius: 1rem;
  padding: 1rem;
  width: 12.5rem;
}
h2 {
  margin-top: 3rem;
  margin-left: 1rem;
}
.carousel-link {
  font-size: 1rem;
  text-align: left;
  margin: 1rem 0;
  color: black;
  text-decoration: underline hotpink;
}

/* bigger screens */
@media screen and (min-width: 43.75em) {
  /* speaker carousel */
  .speaker-carousel {
    max-width: 70rem;
    display: flex;
    flex-wrap: wrap;
    margin: auto;
    padding-left: 1rem;
    padding-bottom: 2rem;
    overflow: hidden;
  }
  .speaker-carousel img {
    border-radius: 1rem;
  }
  .carousel-card {
    margin-right: 1rem;
    font-family: "Black Ops One", system-ui;
    display: flex;
    flex-direction: column;
    border: none;
    border-radius: 1rem;
  }
  h2 {
    margin-top: 3rem;
    margin-left: 1rem;
  }

  .carousel-link {
    font-size: 1rem;
    text-align: left;
    margin: 1rem 0;
    color: black;
    text-decoration: underline hotpink;
  }
}
@media screen and (min-width: 71.5em) {
  h2 {
    max-width: 70rem;
    margin: 2rem auto;
  }
  .speaker-carousel {
    padding-left: 0;
  }
}
</style>
