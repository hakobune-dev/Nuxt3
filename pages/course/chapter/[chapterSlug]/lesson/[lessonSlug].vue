<template> 
<div>
    <p class="mt-0 uppercase font-bold text-slate-400 mb-1">
        Lesson {{ chapter.number }} - {{ lesson.number }}
    </p>
    <h2 class="my-0 font-bold text-2xl">{{ lesson.title }}</h2>
    <div class="flex space-x-4 mt-2 mb-8">
        <NuxtLink  v-if="lesson.sourceUrl" 
        class="font-normal text-md text-gray-500"
        :to="lesson.sourceUrl">
      View the Lecture </NuxtLink>
      <NuxtLink v-if="lesson.downloadUrl" 
        class="font-normal text-md text-gray-500 underline"
        :to="lesson.downloadUrl">
      Download the video </NuxtLink>
    </div>
    <VideoPlayer
    v-if="lesson.videoId"
    :video-id="lesson.videoId"/><br>

    <p>{{ lesson.text }}</p>
</div>
   
</template>

<script setup >
const course = useCourse();
const route = useRoute();
const chapter = computed(()=>{
    return course.chapters.find(
        (chapter) => chapter.slug === route.params.chapterSlug
    );
});
const lesson = computed(()=>{
    return chapter.value?.lessons.find(
        (lesson) => lesson.slug === route.params.lessonSlug
    );
});
const title =computed(()=> {
    return `${lesson.value.title} - ${course.title}`;
});
useHead({
    title,
});
</script>