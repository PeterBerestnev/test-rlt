<template>
  <div class="border size bg-main d-flex f-col">
    <img class="border pic" src="../pics/Blur.png" />
    <div style="height: 26px; width:100%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 10px; width:75%" class="mt emptyField bg-dark"></div>
    <div style="height: 10px; width:90%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 10px; width:85%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 10px; width:80%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 10px; width:75%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 10px; width:50%" class="mt emptyField bg-dark"></div>
  </div>
</template>

<script>
export default {
  name: 'InfoBar',
}
</script>

<style scoped>
.size {
  padding: 2%;
  box-sizing: border-box;
  position: relative;
  min-width: 236px;
  max-height: 500px;
}
.elemBgColor {
  background-color: #4D4D4D;
}
.pic {
  height:50%;
  width: 100%;
}
.f-col {
  flex-direction: column; 
  align-items: center;
}
</style>
