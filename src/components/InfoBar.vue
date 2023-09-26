<template>
  <div class="border size bg-main d-flex f-col">
    <img src="https://bogatyr.club/uploads/posts/2023-03/thumbs/1678826748_bogatyr-club-p-fon-dlya-storis-kosmos-foni-vkontakte-1.jpg" class="border pic"/>
    <div style="height: 20px%; width:100%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 8px; width:75%" class="mt emptyField bg-dark"></div>
    <div style="height: 8px; width:90%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 8px; width:85%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 8px; width:80%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 8px; width:75%" class="mt-1 emptyField bg-dark"></div>
    <div style="height: 8px; width:50%" class="mt emptyField bg-dark"></div>
  </div>
</template>

<script>
export default {
  name: 'InfoBar',
}
</script>

<style scoped>
.size {
  width:31%;
  padding: 2%;
  box-sizing: border-box;
  position: relative;
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
