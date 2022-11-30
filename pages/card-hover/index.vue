<template>
  <div class="container">
    <div class="card">
      <div class="card-header">
        <span>Article 1</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 2</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 3</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 4</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 5</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 6</span>
      </div>
    </div>
    <div class="card">
      <div class="card-header">
        <span>Article 7</span>
      </div>
    </div>

  </div>
</template>

<script setup lang="ts">
</script>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
}
.card {
  height: 300px;
  width: 200px;
  border: 1px solid black;
  box-shadow: -1rem 0 3rem #252525;
  background-color: #305F70;
  transition: 0.5s;
  transform: translateY(0px);
  border-radius: 15px;
  padding: 20px;
}
.card:not(:last-child) {
  margin-right: -150px;
}
.card:hover {
  margin-right: 0px;
  transform: translateY(-50px);
}
.card-header {
  color: white;
  font-size: 0.7em;
  text-transform: uppercase;
  font-weight: bolder;
}
</style>
