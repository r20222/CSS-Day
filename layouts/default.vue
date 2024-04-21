<template>
  <nav>
    <NuxtLink to="/" class="css-day-homelink">CSS Day</NuxtLink>
    <ul>
      <NuxtLink to="/years">Years</NuxtLink>
      <NuxtLink to="/speakers">Speakers</NuxtLink>
      <NuxtLink to="/talks">Talks</NuxtLink>
    </ul>
  </nav>
  <slot />

  <footer>💖 R20222</footer>
</template>

<script setup></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Black+Ops+One&display=swap");

:root {
  --pale-purple: #e8d7f1;
  --thistle: #d3bccc;
  --pomp-and-power: #a167a5;
  --tekhelet: #4a306d;
  --prussian-blue: #0e273c;
  --background-color: #0d0d0d;
}
html {
  font-family: "Black Ops One", system-ui;
  font-weight: 400;
  font-style: normal;
  background-color: var(--background-color);
  color: white;
  scrollbar-gutter: stable;
}
body {
  padding: 0;
  margin: 0;
}
nav {
  padding-top: 1rem;
}
nav ul {
  padding: 0;
}
nav a {
  color: white;
  margin: 1rem;
}
.css-day-homelink {
  margin: 1rem;
  font-size: 3rem;
}
.router-link-active {
  color: hotpink;
}

/* color button links styling */
.ul-styling-buttons {
  padding: 2rem 1rem 1rem;
  list-style: none;
}
.link-style-buttons {
  padding: 2rem;
  display: flex;
  justify-content: center;
  font-size: 1.5rem;
}
.li-styling-buttons {
  border-radius: 1rem;
  margin-bottom: 1rem;
}
.li-styling-buttons:nth-child(5n) {
  background-color: var(--pale-purple);
}
.li-styling-buttons:nth-child(5n + 1) {
  background-color: var(--thistle);
}
.li-styling-buttons:nth-child(5n + 2) {
  background-color: var(--pomp-and-power);
}
.li-styling-buttons:nth-child(5n + 3) {
  background-color: var(--tekhelet);
}
.li-styling-buttons:nth-child(5n + 4) {
  background-color: var(--prussian-blue);
}
.li-styling-buttons:nth-child(5n + 3) a,
.li-styling-buttons:nth-child(5n + 4) a {
  color: white;
}
.li-styling-buttons:nth-child(5n + 1) a,
.li-styling-buttons:nth-child(5n + 5) a,
.li-styling-buttons:nth-child(5n + 6) a,
.li-styling-buttons:nth-child(5n + 2) a {
  color: black;
}

/* colors */
.red {
  color: #ff0000;
  -webkit-text-stroke: 0.01px white;
}
.navy {
  color: #000080;
  -webkit-text-stroke: 0.01px white;
}
.olivedrab {
  color: #6b8e23;
  -webkit-text-stroke: 0.01px white;
}
.hotpink {
  color: #ff69b4;
  -webkit-text-stroke: 0.01px white;
}
.goldenrod {
  color: #daa520;
  -webkit-text-stroke: 0.01px white;
}
.tomato {
  color: #ff6347;
  -webkit-text-stroke: 0.01px white;
}
.deepskyblue {
  color: #00bfff;
  -webkit-text-stroke: 0.01px white;
}
.mediumseagreen {
  color: #3cb371;
  -webkit-text-stroke: 0.01px white;
}
.darkorchid {
  color: #9932cc;
  -webkit-text-stroke: 0.01px white;
}
.peru {
  color: #cd853f;
  -webkit-text-stroke: 0.01px white;
}
.speaker-links {
  color: white;
  display: block;
}
.info-section {
  padding: 0 1rem;
  margin-bottom: 3rem;
}
.info-section img {
  width: 100%;
}
footer {
  padding-top: 8rem;
  padding-bottom: 2rem;
  padding-left: 1rem;
}
/* desktop responsive */
.ul-styling-buttons,
nav,
footer {
  max-width: 70rem;
  margin: auto;
}

/* bigger screens */
@media screen and (min-width: 43.75em) {
  h1 {
    max-width: 70rem;
    margin: 2rem auto 2rem;
    padding-left: 1rem;
    padding-top: 2rem;
  }
  .info-section {
    max-width: 70rem;
    display: grid;
    grid-template-columns: repeat(2, calc(50% - 2rem));
    grid-gap: 0 3rem;
    margin: auto;
  }
}

@media screen and (min-width: 71.5em) {
  nav a,
  .css-day-homelink {
    margin-left: 0;
    margin-right: 2rem;
  }
  h1 {
    padding-left: 0rem;
  }
}
</style>
