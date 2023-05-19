
<template>
   <iframe width="560"
   height="315"
   
   :src="`https:/player.vimeo.com/${props.videoId}`" 
   title="Video player"
   frameborder="0"
   allow="accelerometer; autoplay; clipboard-write;"
   allowfullscreen></iframe>
</template>
<script lang="ts" setup>
const props = defineProps({
    videoId: {
        type: String,
        required: true,
    }
})
</script>