<template>
  <div>
    <indexHeaderBox></indexHeaderBox>
    <cardFloorBox></cardFloorBox>
    <cardFloorBox></cardFloorBox>
    <cardFloorBox></cardFloorBox>
  </div>
</template>

<script>
import indexHeader from '../components/indexHeader'
import cardFloor from '../components/cardFloor/cardFloor'
export default {
  name: 'PageIndex',
  components: {
    'indexHeaderBox': indexHeader,
    'cardFloorBox': cardFloor
  },
  data () {
    return {
      lorem: '嘿嘿嘿'
    }
  }
}
</script>
