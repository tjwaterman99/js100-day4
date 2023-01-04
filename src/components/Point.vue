<script setup lang="ts">
import { ref } from 'vue'

let props = defineProps(['point'])

function click(event: any) {
    console.log(props.point)
}
</script>

<template>
    <div class="point" @click="click">
        {{ point.x }},{{ point.y }}
    </div>
</template>

<style scoped>
    .point {
        padding: 20px;
    }
</style>