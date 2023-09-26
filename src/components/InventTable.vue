<template>
  <div class="bg-main invent border">
    <div style="display: flex; flex-direction: row; height:20%;" v-for="r in 5" :key="r">
      <div :class="{
        'no-border-left': c === 1,
        'no-border-right': c === 5,
        'no-border-top': r === 1,
        'no-border-bottom': r === 5,
        'corner-left-top': (r === 1 && c === 1),
        'corner-right-top': (r === 1 && c === 5),
        'corner-left-bot': (r === 5 && c === 1),
        'corner-right-bot': (r === 5 && c === 5)
      }" class="cell" @drop="onDrop($event, getId(r, c))" @dragover.prevent @dragenter.prevent v-for="c in 5"
        :key="c">
        <div @dragstart="onDragStart($event, getElement(r, c))" draggable="true">
          <div v-if="isElementCell(r, c)" >
            <img :src="getElement(r, c).pic">
          {{ getElement(r, c).count }}
          </div>
 
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  name: 'InventTable',
  data() {
    return {
      elements: [
        { id: 1, value: 0 ,count:4,pic: require('@/pics/mage.png')},
        { id: 9, value: 1 ,count:1,pic:require('@/pics/mage1.png')},
        { id: 20, value: 2,count:6,pic:require('@/pics/mage2.png')}
      ]
    }
  },
  methods: {
    isElementCell(row, column) {
      return this.elements.some(el => el.id === ((row - 1) * 5 + column));
    },
    getElement(row, column) {
      return this.elements.find(el => el.id === ((row - 1) * 5 + column));
    },
    getId(row, column) {
      return (row - 1) * 5 + column;
    },
    onDragStart(e, item) {
      e.dataTransfer.dropEffect = 'move'
      e.dataTransfer.effectAllowed = 'move'
      e.dataTransfer.setData('itemId', item.id)
      },
    onDrop(e, index) {
      const itemId = e.dataTransfer.getData('itemId');
      const item1 = this.elements.find((value) => value.id == itemId);
      const item2 = this.elements.find((value) => value.id == index);
      const firstElIndex = this.elements.indexOf(item1);
      const secondElIndex = this.elements.indexOf(item2);
      if(secondElIndex != -1 && firstElIndex != -1)
      {
        // Swap the elements in the array
        this.elements.splice(firstElIndex, 1, { id: item1.id, value: item2.value , count: item2.count, pic: item2.pic});
        this.elements.splice(secondElIndex, 1, { id: item2.id, value: item1.value, count: item1.count, pic: item1.pic });
      }
      else if(firstElIndex != -1){
        this.elements[firstElIndex].id = index
      }
   
    },
  },

}
</script>
  
<style scoped>
.invent {
  width: 100%;
  margin-left: 30px;
  border-radius: 12px;
}

.cell:hover {
  background-color: #2f2f2f;
}

.cell {
  display: flex;
  flex-direction: column;
  width: 100%;
  justify-content: center;
  align-items: center;
  border: 1px solid #4D4D4D
}

.no-border-left {
  border-left: none;
}

.no-border-right {
  border-right: none;
}

.no-border-top {
  border-top: none;
}

.no-border-bottom {
  border-bottom: none;
}

.corner-left-top:hover {
  background-color: #2F2F2F;
  border-top-left-radius: 12px;
}

.corner-right-top:hover {
  background-color: #2F2F2F;
  border-top-right-radius: 12px;
}

.corner-left-bot:hover {
  background-color: #2F2F2F;
  border-bottom-left-radius: 12px;
}

.corner-right-bot:hover {
  background-color: #2F2F2F;
  border-bottom-right-radius: 12px;
}
</style>
  