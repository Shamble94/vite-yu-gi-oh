<script>
import { store } from "../store.js"
export default{
    data(){
      return{
        /* RICHIAMO LO STORE PER POTERLO UTILIZZARE */
        store
      }
    }
    
}
</script>
<template lang="">
  <div>
    <div class="container">
       <div class="row">
           <div class="col-4">
              <!-- LABEL ARCHETYPE -->
              <label for="filter" class="control-label"> Archetype </label>
              <!-- SELECT CONTENENTE GLI ARCHETYPE PRESI DALL'API -->
              <select id="filter" class="form-select" v-model="store.search">
                <option value="" selected>Select Archetype</option>
                <option v-for = "archetype, index in  store.archeList" :key="index" :value="archetype.archetype_name" >
                  {{ archetype.archetype_name }}
                </option>
              </select>
           </div>
            <div class="col-3">
              <!-- BOTTONE CON EMIT PER RICERCARE LE CARD IN BASE ALL'ARCHETYPE -->
              <button class="btn btn-primary mt-4" @click="$emit(`SearchArchetype`)"> Search</button>

            </div>
       </div>
    </div>
  </div>
</template>
<style lang ="scss" scoped>
.row{
    display: flex;
   justify-content: center;
  
}
</style>