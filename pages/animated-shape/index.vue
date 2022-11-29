<template>
  <div class="box">
    <div class="spin-container">
      <div class="shape">
        <div class="bd">
          Je suis un texte
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
* {
  box-sizing: border-box;
}
body {
  background: #003;
}

.box {
  width: 300px;
  height: 300px;
  border: 1px dashed rgba(255,255,255,0.4);
  position: relative;
}

.spin-container {
  width: 100%;
  height: 100%;
  animation: spin 12s linear infinite;
  position: relative;
}

.shape {
  width: 100%;
  height: 100%;
  transition: border-radius 1s ease-out;
  border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
  animation: morph 8s ease-in-out infinite both alternate;
  position: absolute;
  overflow: hidden;
  z-index: 5;
}

.bd {
  width: 142%;
  height: 142%;
  position: absolute;
  left: -21%;
  top: -21%;
  background-size: 100%;
  background: url(https://picsum.photos/400/400) center center;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #ffffff;
  text-align: center;
  font-weight: bold;
  font-family: sans-serif;
  text-transform: uppercase;
  animation: spin 12s linear infinite reverse;
  opacity: 1;
  z-index: 2;
}

@keyframes morph {
  0% {border-radius: 40% 60% 60% 40% / 60% 30% 70% 40%;}
  100% {border-radius: 40% 60%;}
}

@keyframes spin {
  to {
    transform: rotate(1turn);
  }
}
</style>
