<template>
  <div class="properties bg-main">
    <input class="emptyField bg-dark" type="text">
    <img class="cross" src="../pics/Vector.svg">
  </div>
</template>
  
<script>
export default {
  name: 'DownBar',
}
</script>
  
<style scoped>
.properties {
 
  width: 100%;
  min-height: 72px;
  padding: 10px 20px 10px 20px;
  border: 1px solid #4D4D4D;
  border-radius: 12px;
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.cross {
  margin-left: auto;
  margin-bottom: 30px;
}
</style>
  