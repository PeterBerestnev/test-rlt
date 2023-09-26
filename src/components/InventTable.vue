<template>
  <div class="bg-main invent">
    <table class="border">
      <tr v-for="row in 5" :key="row">
        <td v-for="column in 5" :key="column" :class="{ 'no-border-left': column === 1, 'no-border-right': column === 5, 'no-border-top': row === 1, 'no-border-bottom': row === 5 }">
          {{ row }}, {{ column }}
        </td>
      </tr>
    </table>
  </div>
</template>
  
<script>
export default {
  name: 'InventTable',
}
</script>
  
<style scoped>
table {
  width: 100%;
  height: 100%;
  border-spacing: 0
}
.invent {
  width: 100%;
  margin-left: 30px;
  border-radius: 12px;
}

td {
  border: 1px solid #4D4D4D;
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
</style>
  