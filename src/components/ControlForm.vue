<template>
    <TransitionGroup name="slide-right">
        <div v-if="isOpen" class="modal" :key="1"></div>
        <div v-if="isOpen" class="params" :key="2">
            <img @click="closeModal" class="cross" src="../pics/Vector.svg">
            <img class="pic"  :src="item.pic">
            <div class="divider"></div>
            <div class="stub bg-dark"></div>
            <div class="options">
                <div class="smstub bg-dark"></div>
                <div class="smstub bg-dark"></div>
                <div class="smstub bg-dark"></div>
                <div class="smstub w-70 bg-dark"></div>
                <div class="smstub w-40 bg-dark"></div>
            </div>
            <div class="divider"></div>
            <button class="btn"><div class="txt">Удалить предмет</div></button>
        </div>
    </TransitionGroup>
</template>
    
<script>
export default {
    name: 'ControlForm',
    props: {
        item: {
            type: Object,
            required: true,
        },
    },
    data() {
        return {
            isOpen: false
        }
    },
    methods: {
    openModal() {
      this.isOpen = true;
    },
    closeModal() {
      this.isOpen = false;
    }
  }
}
</script>
    
<style scoped>
.slide-right-enter-active,
.slide-right-leave-active {
  transition: all 0.5s;
}

.slide-right-enter-from,
.slide-right-leave-to {
  transform: translateX(40px);
  opacity: 0;
}
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.params {
    position: relative;
    max-width: 250px;
    margin-left: auto;
    height: 100%;
    bottom: 99.9%;
    background-color: white;
    border-left: 1px solid #4D4D4D;
    z-index: 1;
    background: linear-gradient(0deg, rgba(38, 38, 38, 0.9), rgba(38, 38, 38, 0.98));
    border-bottom-right-radius: 12px;
    border-top-right-radius: 12px;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
}
.options {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}
.btn {
    background-color: #FA7272;
    border-radius: 8px;
    width: 220px;
    height: 39px;
    color: #FFFFFF;
    border: 0;
}
.btn:hover {
    background-color: #FF8888
}
.txt {
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 400;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: center;
}
.pic {
    width: 60%;
    align-self: center;
    margin-top: 40px
}
.cross:hover {
    scale: 1.3
}
.stub {
    width: 80%;
    height: 30px;
    top: 232px;
    left: 19px;
    border-radius: 8px;
    margin-top:20px;
    align-self: center
}
.divider {
    width: 90%;
    height: 1px;
    top: 215px;
    left: 15px;
    background: #4D4D4D;
    margin-top: 20px;
    align-self: center;
}
.smstub {
    width: 80%;
    height: 10px;
    border-radius: 4px;
    margin-top: 15px;
}
.w-70 {
    width: 70%;
}
.w-40 {
    width: 40%;
}
.cross {
    margin-left: 95%;
    
}
</style>
    