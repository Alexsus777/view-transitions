<template>
  <div class="flex flex-wrap gap-12">
    <div :ref="(el) => itemRefs[i] = el as HTMLElement" @click="cardClick(i)" v-for="(item, i) in 12"
      class="w-[150px] card cursor-pointer border-2 rounded p-2 flex flex-col items-center justify-center bg-blue-500">

      <img src="~/assets/images/test.jpeg" />
      <p class="capitalize text-lg">title</p>
    </div>
  </div>
</template>


<script lang="ts" setup>
const itemRefs = ref<HTMLElement[]>([])
const currentIndex = ref()


async function cardClick(index: number) {
  const cardAnimation = (document as any).startViewTransition(() => {
    if (itemRefs.value[index].classList.contains('big-card')) {
      itemRefs.value[index].classList.remove('big-card')
    } else {
      itemRefs.value[index].classList.add('big-card')
      currentIndex.value = index
    }

    // itemRefs.value[index].style.display = 'none'
  })

  try {
    await cardAnimation.finished;
  } finally {
    // alert('animation done')
  }
}
</script>

<style>
/* ::view-transition-old(root),
::view-transition-new(root) {
  animation-duration: 3000ms;
} */
</style>