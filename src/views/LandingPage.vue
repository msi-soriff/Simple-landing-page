<!-- LandingPage.vue -->
<template>
    <div class="landing-page">
        <div v-for="car in cars" :key="car.id">
            <car-info :car="car" />
        </div>
    </div>
</template>
  
<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';
import axios from 'axios';
import CarInfo from '@/components/CarInfo.vue';

export default defineComponent({
    components: {
        CarInfo,
    },
    setup() {
        const cars = ref([]);

        onMounted(async () => {
            try {
                const response = await axios.get('your_api_endpoint_here');
                cars.value = response.data;
            } catch (error) {
                console.error('API Error:', error);
            }
        });

        return {
            cars,
        };
    },
});
</script>
  