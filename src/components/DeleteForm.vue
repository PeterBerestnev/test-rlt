<template>
    <div class="param">
        <input :class="{error: inCorrect}" v-model="numToDel" class="bg-dark input mt-1" type="number" placeholder="Введите количество">
        <div class="buttons">
            <button @click="abroat" class="btn white"><div class="txt">Отмена</div></button>
            <button @click="deleteReps" class="btn"><div class="txt">Подтвердить</div></button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DeleteForm',
    props: {
        count: {
            type: Number,
            required: true
        }
    },
    data() {
        return {
            numToDel: null,
            inCorrect: false
        }
    },
    methods: {
        deleteReps() {
            if(this.numToDel !== null && this.numToDel >= 0 && this.numToDel <= this.count) {
                this.inCorrect = false
                this.$emit('deleteReps', this.numToDel)
            }
            else {
                this.numToDel = null
                this.inCorrect = true
            }
        },
        abroat() {
            this.$emit('abroat')
        }
    },
    inheritAttrs: false,
}
</script>

<style scoped>
.buttons {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content:space-around;
    margin-top: 15px;
}
.param {
    align-items: center;
    height: 133px;
    background: linear-gradient(0deg, rgba(38, 38, 38, 0.6), rgba(38, 38, 38, 0.6));
    border-top: 1px solid #4D4D4D
}
.input {
    color:white;
    width:210px;
    height: 40px;
    border-radius: 4px;
    border: 1px solid #4D4D4D;
    background: linear-gradient(0deg, #262626, #262626);
    font-family: Inter;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: center;
}
.error {
    border:#FA7272 1px solid
}
.btn {
    background-color: #FA7272;
    border-radius: 8px;
    color: #FFFFFF;
    border: 0;
    padding: 4px 14px 4px 14px;
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 400;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: left;
}
.btn:hover {
    background-color: #FF8888
}
.white {
    background: #FFFFFF;
    font-family: SF Pro Display;
    font-size: 14px;
    font-weight: 400;
    line-height: 17px;
    letter-spacing: 0em;
    text-align: left;
    color: #262626;
}
.white:hover {
    background: #ebe7e7;
}
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
}
</style>
