<template>
  <div class="q-pa-md">
    <q-parallax :height="150">
      <template v-slot:media>
        <video width="720" height="440" poster="https://cdn.quasar.dev/img/polina.jpg" loop muted>
          <source type="video/webm" src="https://cdn.quasar.dev/img/polina.webm">
          <source type="video/mp4" src="https://cdn.quasar.dev/img/polina.mp4">
        </video>
      </template>

      <i class="fas fa-caret-right playIcon"></i>
    </q-parallax>
  </div>
</template>
<style  lang="stylus" scoped>
.playIcon
  font-size : 5rem;
</style>
