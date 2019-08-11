<template>
  <div class="cardTem">
    <div class="q-pa-md">
      <q-card class="my-card">
        <div class="iconDiv">
          <i class="fas fa-caret-right playIcon"></i>
          <img src="statics/mountains.webp">
        </div>
        <q-card-section style="color:#000000">
          <div class="text-h6">Our Changing Planet</div>
          <div class="text-subtitle2">by John Doe</div>
        </q-card-section>
        <q-card-section style="color:#000000">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'cardTem'
}
</script>
<style lang="stylus" scoped>
.cardTem {
  padding: 0px 30px;
  display: inline-block;
}

.q-pa-md {
  display: inline-block;
}

.my-card {
  width: 100%;
  max-width: 300px;
}
.iconDiv{
  width : 100%;
  height : 100%
  position : relative;
}
.iconDiv img{
  display: block;
  width: 100%;
  max-width: 100%;
  border: 0;
}
.playIcon {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 5rem;
}
</style>
