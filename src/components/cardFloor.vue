<template>
  <div class="q-pa-md">
    <q-card class="my-card">
      <videoTem></videoTem>
      <q-card-section>
        <div class="text-h6">Our Changing Planet</div>
        <div class="text-subtitle2">by John Doe</div>
      </q-card-section>
      <q-card-section>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
        eiusmod tempor incididunt ut labore et dolore magna aliqua.
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import videoTem from './videoTem'
export default {
  name: 'cardFloor',
  components: {
    'videoTem': videoTem
  }
}
</script>
<style lang="stylus" scoped>
.my-card {
  width: 100%;
  max-width: 300px;
}
</style>
