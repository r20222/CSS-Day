<template>
  <section v-for="dataObject in data">
    <!-- $route.params.id hiermee haal je data uit de slug op -->
    <h1
      v-if="dataObject.name === $route.params.id"
      :class="dataObject.edition.color.name"
    >
      {{ dataObject.name }}
    </h1>

    <!-- deze code haalt alle data op die in het object staan waarbij de naam waarde overeenkomt met de waarde uit de slug -->
    <section class="info-section" v-if="dataObject.name === $route.params.id">
      <!-- speaker avatar -->
      <img alt="" :src="dataObject.avatar" />

      <article>
        <!-- date of CSS days attended-->
        <section>
          <h2 :class="dataObject.edition.color.name">Date:</h2>
          <p
            class="dates"
            v-if="Array.isArray(dataObject.edition.date)"
            v-for="date in dataObject.edition.date"
          >
            {{ date }}
          </p>
          <p class="dates" v-else>{{ dataObject.edition.date }}</p>
        </section>

        <section>
          <h2 :class="dataObject.edition.color.name">Edition:</h2>
          <NuxtLink
            :to="`/years/${dataObject.edition.year}`"
            class="speaker-links"
            >{{ dataObject.edition.title }}</NuxtLink
          >
        </section>

        <!-- venue of CSS days -->
        <section>
          <h2 :class="dataObject.edition.color.name">Venue:</h2>
          <p>{{ dataObject.edition.venue }}</p>
        </section>

        <!-- title & description of presentation -->
        <h2 class="title-description" v-if="dataObject.talk.title">
          {{ dataObject.talk.title }}
        </h2>
        <p v-if="dataObject.talk.description">
          {{ dataObject.talk.description }}
        </p>

        <!-- link to slides & youtube presentation video -->
        <a
          class="speaker-links"
          v-if="dataObject.talk.slides"
          :href="dataObject.talk.slides"
          target="_blank"
          >Slides of the presentation</a
        >
        <a
          class="speaker-links"
          v-if="dataObject.talk.video['youtube-link']"
          :href="dataObject.talk.video['youtube-link']"
          target="_blank"
          >Presentation Video</a
        >
      </article>
    </section>
  </section>
</template>

<script setup>
const { data } = await useFetch("https://cssday.nl/data/speakers.json");
</script>

<style scoped>
h1 {
  padding-left: 1rem;
  font-size: 2rem;
  margin: 2rem auto;
}
img {
  border-radius: 1rem;
}
.info-section section {
  margin-top: 2rem;
}
.info-section section p,
.info-section section a {
  line-height: 0;
}
.title-description {
  margin-top: 4rem;
}

/* bigger screens */
@media screen and (min-width: 43.75em) {
  article {
    position: relative;
    top: -2rem;
  }
}

@media screen and (min-width: 71.5em) {
  h1 {
    padding-left: 0rem;
  }
}
</style>
