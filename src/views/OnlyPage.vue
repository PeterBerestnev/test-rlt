<template>
    <div class="rootElem d-flex">
        <div class="d-flex f-column">
            <div class="d-flex">
                <InfoBar></InfoBar>
                <InventTable></InventTable>
            </div>
            <DownBar class="mt"></DownBar>
        </div>
    </div>
</template>

<script>
import InfoBar from '../components/InfoBar.vue'
import DownBar from '../components/DownBar.vue'
import InventTable from '../components/InventTable.vue'

export default {
    name: 'OnlyPage',
    components: {
        InfoBar,
        DownBar,
        InventTable
    }
}
</script>

<style scoped>
#app,
html,
body {
    height: 100%;
}

.rootElem {
    height: 100vh;
    justify-content: center;
    box-sizing: border-box;
}

.d-flex {
    display: flex;
}

.f-row {
    flex-direction: row;
}

.f-column {
    flex-direction: column;
    align-self:center
}
</style>
