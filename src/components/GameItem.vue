<script setup>
import { ref } from 'vue'

const props = defineProps({
  game: {
    type: Object,
    required: true
  }
})

const showAd = ref(false)

const handleClick = () => {
  showAd.value = true
}
</script>

<template>
  <div>
    <div @click="handleClick">
      <LinkWidget :href="'/' + props.game.link" class="aspect-square">
        <img
          class="h-full w-full rounded-2xl shadow-md"
          v-lazy="props.game.thumb"
          :alt="props.game.title"
        />
      </LinkWidget>
    </div>
    <div v-if="showAd" id="ad-container" style="width:480px; height:320px; text-align:center;">
      <ins class="adsbygoogle"
           style="display:inline-block;width:480px;height:320px"
           data-ad-client="ca-pub-2383602858776570"
           data-ad-slot="chaye_03"></ins>
      <script>
        (adsbygoogle = window.adsbygoogle || []).push({});
      </script>
    </div>
  </div>
</template>

<style scoped>
/* 可以添加一些组件的局部样式 */
</style>
