<template>
    <div class="bg-white border border-dark rounded d-flex">
      <img class="img-fluid house-img rounded-start" :src="houseProp.imgUrl" :alt="houseProp.description">
      <div class="p-3">
        <div class="mb-3">
          <h2>{{ houseProp.bedrooms }} {{ houseProp.bathrooms }} {{ houseProp.levels }}</h2>
          <p>{{ houseProp.price }}</p>
          <!-- <h3>Listed by: {{ houseProp.creatorId }} on {{ houseProp.createdAt.toLocaleDateString() }}</h3> -->
          <!-- <img class="creator-picture" :src="carProp.creator.picture" :alt="carProp.creator.name"> -->
        </div>
        <!-- <div v-if="account.id == houseProp.creatorId"> -->
  
          <!-- <button @click="removeCar()" class="btn btn-danger" title="Delete this car" type="button"> -->
            <!-- <i class="mdi mdi-delete"></i> -->
          <!-- </button> -->
  
          <!-- <button @click="setCarToEdit()" class="btn btn-info ms-3" title="Edit car" type="button" data-bs-toggle="modal"
            data-bs-target="#formModal">
            <i class="mdi mdi-pencil"></i>
          </button> -->
        </div>
      </div>
    <!-- </div> -->
  </template>

  <script>
import { AppState } from '../AppState.js';
import { House } from '../models/House.js';
import { housesService } from '../services/HousesService.js';
import { logger } from '../utils/Logger.js';
import Pop from '../utils/Pop.js';
import { computed } from 'vue'

export default {
    props: {
        houseProp: { type: House,
        },
        setup(props) {
            return {
                account: computed(() => AppState.account),
            }
        }
    }
}

</script>

<style lang="scss" scoped></style>