<template>
  <div class="container">
    <div class="shape">
      <div class="content">
        Hello world
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Custom animation styles kept in plain CSS */
.container {
  width: 300px;
  height: 300px;
  position: relative;
}
.shape {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
  animation: morph 8s ease-in-out infinite both alternate, spin 12s infinite linear;
}
.content {
  position: absolute;
  width: 142%;
  height: 142%;
  top: 50%;
  left: 50%;
  animation: reverseSpinAndTranslate 12s infinite linear;
  background: url("https://picsum.photos/350") center no-repeat;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1em;
  text-transform: uppercase;
  font-weight: bolder;

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

@keyframes reverseSpinAndTranslate {
  from {
    transform: translate(-50%, -50%) rotate(1turn);
  }
  to {
    transform: translate(-50%, -50%) rotate(0turn);
  }
}

</style>
