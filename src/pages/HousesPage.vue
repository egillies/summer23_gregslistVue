<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12">
                <h1>Houses</h1>
            </div>
        </div>
        <div class="row">
            <div v-for="house in houses" :key="house.id" class="col-10">
                <div class="row">
                    <img class="img-fluid" :src="house.imgUrl" alt="house.description">
               <HouseCard :houseProp="house" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { logger } from '../utils/Logger.js';
import Pop from '../utils/Pop.js';
import { housesService } from '../services/HousesService.js'
import { AppState } from '../AppState.js';
import {computed, onMounted} from 'vue'





export default {
    setup(){
        async function getHouses(){
            try {
               await housesService.getHouses();
            }
         catch (error) {
            Pop.error(error);
        }
    }

        onMounted(() => {
            logger.log('home page mounted')
            getHouses();
        });
        return {
            houses: computed(() => AppState.houses),
            account: computed(() => AppState.account),
        }
    }
    
}
</script>

<style lang="scss" scoped></style>