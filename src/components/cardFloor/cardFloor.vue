<template>
  <div class="floor">
    <q-card dark bordered class="bg-grey-1 my-card">
      <q-card-section>
        <div class="text-h6" style="color:#000">Parking Spaces No.1</div>
      </q-card-section>

      <q-separator dark inset color="black"/>

      <q-card-section>
        <cardTemBox></cardTemBox>
        <cardTemBox></cardTemBox>
        <cardTemBox></cardTemBox>
        <cardTemBox></cardTemBox>
      </q-card-section>
    </q-card>
  </div>
</template>
<script>
import cardTem from './cardTem'
export default {
  name: 'cardFloor',
  components: {
    'cardTemBox': cardTem
  },
  data () {
    return {
      lorem: '我是小菜比'
    }
  }
}
</script>
<style  lang="stylus" scoped>
.floor
  padding: 16px;
.my-card
  width 100%
  max-width 100%
</style>
