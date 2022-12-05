<template>
  <div>
    <nav>
      <NuxtLink to="/">Home page</NuxtLink>
      <NuxtLink to="section">Section</NuxtLink>
      <NuxtLink to="card-hover">Card-hover</NuxtLink>
      <NuxtLink to="side-slider">side-slider</NuxtLink>
      <NuxtLink to="updown-slider">updown-slider</NuxtLink>
      <NuxtLink to="section-scroll">section-scroll</NuxtLink>
      <NuxtLink to="animated-shape">animated-shape</NuxtLink>
    </nav>
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<style>
nav {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 2em;
  margin-bottom: 2em;
}
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;

}
</style>
