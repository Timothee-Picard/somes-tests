<template>
  <div>
    <nav>
      <NuxtLink to="/">Home page</NuxtLink>
      <NuxtLink to="/section">Section</NuxtLink>
      <LazyNuxtLink to="animated-shape">animated-shape</LazyNuxtLink>
    </nav>
    <main>
      <NuxtPage />
    </main>
  </div>
</template>

<style>
nav {
  display: flex;
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
