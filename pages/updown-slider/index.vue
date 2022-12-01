<template>
  <button @click="slide < slideLength - 1? slide++ : slide = 0">Up</button>
  <button @click="slide > 0? slide-- : slide = slideLength - 1">Down</button>
  <div class="container">
    <div class="aside">
      <div class="slide" style="--slide-color: #15445f">Slide 1</div>
      <div class="slide" style="--slide-color: #a9a9a9">Slide 2</div>
      <div class="slide" style="--slide-color: rgba(255,0,0,0.15)">Slide 3</div>
      <div class="slide" style="--slide-color: #885959">Slide 4</div>
      <div class="slide" style="--slide-color: rgba(44,50,201,0.6)">Slide 5</div>
    </div>
    <div class="main">
      <div class="slide" style="--slide-color: #3ba8e7">Slide 1</div>
      <div class="slide" style="--slide-color: #f83535">Slide 2</div>
      <div class="slide" style="--slide-color: rgba(92,129,75,0.15)">Slide 3</div>
      <div class="slide" style="--slide-color: #7e6943">Slide 4</div>
      <div class="slide" style="--slide-color: rgba(100,36,36,0.6)">Slide 5</div>
    </div>
  </div>
</template>

<script setup>
 const slide = ref()
 let slideLength = ref(0)
 onMounted(() => {
   slideLength.value = document.querySelectorAll(".aside .slide").length
 })
</script>

<style scoped>
.container {
  display: flex;
  width: 75%;
  height: 600px;
  overflow: hidden;
}
.slide {
  min-height: 600px;
  background-color: var(--slide-color);
}
.main {
  background-color: red;
  transform: translateY(calc(600px * v-bind('slide')));
  display: flex;
  flex-direction: column-reverse;
  flex: 1;
  transition: 0.5s ease-in-out;
}
.aside {
  background-color: blue;
  transform: translateY(calc(-600px * v-bind('slide')));
  display: flex;
  flex-direction: column;
  flex: 0.5;
  transition: 0.5s ease-in-out;
}
</style>
