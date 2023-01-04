<script setup lang="ts">
import { ref } from 'vue'
import Point from './Point.vue'
import { Grid } from '../lib/utils';

let props = defineProps(['rows', 'columns'])

let grid = ref(new Grid(props.rows, props.columns))
</script>


<template>
    <div class="grid">
        <div class="grid-row" v-for="(row, index) in grid.getRows()" :key="index">
            <div class="grid-item" v v-for="(point, index) in row" :key="index">
                <Point :point="point"></Point>
            </div>
        </div>
    </div>
</template>

<style scoped>
.grid {
    border: 1px solid black;
    display: flex;
    flex-direction: row;
}

.grid-row {
    border: 1px solid red;
    margin: 5px;
    flex-grow: 1;
    display: flex;
    flex-direction: column-reverse;
}

.grid-item {
    border: 1px solid blue;
    flex-grow: 1;
}
</style>