<template>
  <p ref="text" @click="changeTextStyle">Index</p>
</template>

<script lang="ts" setup>
const text = ref<HTMLParagraphElement>()

function changeTextStyle() {
  (document as any).startViewTransition(() => {
    (text.value as HTMLParagraphElement).style.fontSize = '30px'
  })
}
</script>