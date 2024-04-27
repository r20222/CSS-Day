<template>
  <section class="introduction">
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
    <h1>I Love CSS</h1>
  </section>
</template>

<style scoped>
.introduction {
  margin: 1rem;
  display: grid;
  grid-template-columns: repeat(2, calc(50% - 0.5rem));
  grid-gap: 0 1rem;
  max-width: 70rem;
}
h1 {
  font-size: 3rem;
  margin: 0;
}
.introduction h1 {
  background-image: linear-gradient(
    -225deg,
    var(--tekhelet) 0%,
    var(--thistle) 25%,
    var(--pomp-and-power) 40%,
    pink 60%,
    hotpink 70%,
    var(--thistle) 80%,
    var(--tekhelet) 100%
  );
  background-size: 400% auto;
  color: #fff;
  -webkit-text-stroke: white 1px;
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: text-background-animation 10s linear infinite;
}

@keyframes text-background-animation {
  to {
    background-position: 200% center;
  }
}

/* bigger screen */
@media screen and (min-width: 43.75em) {
  h1 {
    font-size: 5rem;
  }
  .introduction {
    margin: auto;
    padding-left: 1rem;
  }
}
</style>
