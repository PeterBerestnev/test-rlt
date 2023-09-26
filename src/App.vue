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
  background: linear-gradient(90deg, #3C3C3C 0%, #444444 51.04%, #333333 100%);

}
.emptyField {
  width: 92%;
  height: 36px;
  border: 0px;
  border-radius: 12px;
}
.mt {
    margin-top: 25px
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
