<!-- CarInfo.vue -->
<template>
    <div class="car-info">
        <img :src="car.imageUrl" alt="Car Image" />
        <h3>{{ car.name }}</h3>
        <p>{{ car.description }}</p>
    </div>
</template>
  
<script lang="ts">
import { defineComponent, type PropType } from 'vue';

export default defineComponent({
    props: {
        car: {
            type: Object as PropType<{ imageUrl: string; name: string; description: string }>,
            required: true,
        },
    },
});
</script>
  
<style scoped>
/* Add CSS styles for your car info component */
.car-info {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
    text-align: center;
}
</style>
  