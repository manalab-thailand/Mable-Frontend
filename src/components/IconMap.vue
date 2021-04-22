<template>
  <q-icon 
    name="fas fa-user-tag" 
    class="tag blink" 
    color="orange-8" 
    size="30px"
  >

   <q-popup-proxy class="rounded-borders-20">
           <Map-card
           :id_visitor="id_visitor"
           :id='id'
           :fname='fname'
           :lname='lname'
           :tel='tel'
           :category='category'
           :room='room'
           ></Map-card>
      </q-popup-proxy>
  </q-icon>
</template>

<script>
import MapCard from "../components/MapCard.vue"
export default {
   props: ['id_visitor','id','fname','lname','tel','category','room'],
   components: {
    MapCard
  },
};
</script>

<style>
.tag{
  width: 50px;
  height: 40px;
  
}
.blink {
  animation: blinker 4s linear infinite;
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}</style>