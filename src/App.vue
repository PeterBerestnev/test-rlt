<template>
  <OnlyPage/>
</template>

<script>
import OnlyPage from './views/OnlyPage.vue'

export default {
  name: 'App',
  components: {
    OnlyPage
  }
}
</script>

<style>
body{
  margin:0;
  background-color: rgba(30,30,30,255)
}
.bg-dark {
  background: linear-gradient(to bottom right, #4D4D4D,90%, rgb(39, 37, 37));
}
.emptyField {
  width: 80%;
  border: 0px;
  border-radius: 12px;
  height: 1.5rem
}
.mt {
    margin-top: 30px
}
.mt-1 {
  margin-top: 20px
}
.bg-main {
  background-color: #262626;
}
.border {
  border: solid 1px #4D4D4D;
  border-radius: 12px;
}
</style>
