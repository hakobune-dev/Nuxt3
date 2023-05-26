<template>
    <NuxtLayout>
      <div class="prose">
        <h1><b>Dang</b></h1><br>
        <p>It looks like something broke.</p><br>
        <p>Sorry about that.</p><br>
        <p>
          <strong>{{ error.message }}</strong>
        </p><br>
        <p>
          Go to the
          <a
            class="hover:cursor-pointer"
            @click="handleError"
          >
            <u>first lesson.</u>
          </a>
        </p><br>
      </div>
    </NuxtLayout>
  </template>
  
  <script setup>
  const error = useError();
  const handleError = () => {
    clearError({
      redirect:
        '/course/chapter/1-chapter-1/lesson/1-introduction-to-typescript-with-vue-js-3',
    });
  };
  </script>