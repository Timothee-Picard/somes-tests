<template>
  <div class="container">
    <div class="item 1">
      <img src="https://picsum.photos/700/400?">
    </div>
    <div class="item 2">
      <img src="https://picsum.photos/700/400">
    </div>
    <div class="item 3">
      <img src="https://picsum.photos/700/400?blur=1">
    </div>
    <div class="item 4">
      <img src="https://picsum.photos/700/400?blur=2">
    </div>
    <div class="item 5">
      <img src="https://picsum.photos/700/400?blur=3">
    </div>
  </div>
  <div>
    <button @click="slideLeft">&lt;</button>
    <button @click="slideRight">&gt;</button>
  </div>
</template>

<script setup lang="ts">
let items = ref()
function slideLeft() {
  const oldArray = [...items.value]
  const currentArray = [...items.value]
  currentArray.pop()
  const newArray = [oldArray[oldArray.length-1], ...currentArray]
  displaySlides(newArray)
}

function slideRight() {
  let oldArray = [...items.value]
  let newArray = [...Array.from(items.value).slice(1), oldArray[0]]
  displaySlides(newArray)
}

function displaySlides(array: any[] | NodeListOf<Element>) {
  items = ref(array)
  let arr = items.value;
  let arrCopy = [...arr].reverse();
  if (Number.isInteger(arr.length / 2)) {
  }
  else {
    const middleItem = Math.ceil(arr.length / 2 -1)
    // Centered item
    arr[middleItem].style.transform = `perspective(500px) translate3d(0, 0, 0)`
    arr[middleItem].style.zIndex = arr.length * 2 + 1
    // Left items
    arr.forEach((item: { style: { transform: string; zIndex: any; }; }, i: number) => {
      if(i >= middleItem) return
      item.style.transform = `perspective(500px) translate3d(-${(middleItem- i)*5}0%, -${1* i}00px, -${middleItem - i}00px)`
      item.style.zIndex = arr.length + i
    })
    // Right items
    arrCopy.forEach((item: { style: { transform: string; zIndex: any; }; }, i: number) => {
      if(i >= middleItem) return
      item.style.transform = `perspective(500px) translate3d(+${(middleItem- i)*5}0%, -${1* i}00px, -${middleItem - i}00px)`
      item.style.zIndex = arr.length + i
    })
  }
}
onMounted(() => {
  displaySlides(document.querySelectorAll('.item'))
})
</script>

<style scoped>
.container {
  display: flex;
  position: relative;
  height: 600px;
  width: 100%;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  background-color: #BADB5C;
}
.item {
  position: absolute;
  transition: 0.3s;
  z-index: 99;
}
img {
  max-width: 95vw;
}

</style>
