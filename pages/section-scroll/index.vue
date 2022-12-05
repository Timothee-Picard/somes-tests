<template>
  <section class="active">
    <h2>Section 1</h2>
  </section>
  <section ref="section2">
    <h2>Section 2</h2>
  </section>
  <section ref="section3">
    <h2>Section 3</h2>
  </section>
  <section ref="section4">
    <h2>Section 4</h2>
  </section>
  <section ref="section5">
    <h2>Section 5</h2>
  </section>
</template>

<script setup lang="ts">
import { useWindowScroll } from '@vueuse/core'

const { x, y } = useWindowScroll()

const section2 = ref()
const section3 = ref()
const section4 = ref()
const section5 = ref()

watch(y, () => {
  section2.value.getBoundingClientRect().top < 0 + window.innerHeight/2 ?
      section2.value.classList.add('active') :
      section2.value.classList.remove('active')

  section3.value.getBoundingClientRect().top < 0 + window.innerHeight/2 ?
      section3.value.classList.add('active') :
      section3.value.classList.remove('active')

  section4.value.getBoundingClientRect().top < 0 + window.innerHeight/2 ?
      section4.value.classList.add('active') :
      section4.value.classList.remove('active')

  section5.value.getBoundingClientRect().top < 0 + window.innerHeight/2 ?
      section5.value.classList.add('active') :
      section5.value.classList.remove('active')
})

</script>

<style scoped>
section {
  min-height: 100vh;
  width: 100%;
  background-color: red;
}
section h2 {
  position: relative;
  text-transform: uppercase;
  font-weight: bolder;
  width: fit-content;
}
section h2:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 0.3em;
  background-color: black;
  top: 50%;
  left: 0;
  transform: translateY(-50%);
  transition: 1s ease-in-out;
}
section.active h2:before {
  width: 0%;
}
</style>
