<template>
  <q-icon
    name="fas fa-user-tag"
    class="tag blink row q-gutter-xs"
    color="orange-8"
    size="30px"
  >
<<<<<<< HEAD
    <q-popup-proxy>
      <Map-card
        :id_visitor="id_visitor"
        :id="id"
        :fname="fname"
        :lname="lname"
        :tel="tel"
        :category="category"
        :room="room"
        :contract="contract"
      ></Map-card>
    </q-popup-proxy>
     <q-badge color="green-8" :label="'TAG '+id"  />
=======
      <q-popup-proxy class="rounded-borders-20">
           <Map-card
           :id_visitor="id_visitor"
           :id='id'
           :fname='fname'
           :lname='lname'
           :tel='tel'
           :category='category'
           :room='room'
           :contract='contract'
           ></Map-card>
      </q-popup-proxy>
>>>>>>> 059f54e8d7f6c5a8a86ce481a28b1af5ab67a28a
  </q-icon>
</template>

<script>
import MapCard from "../components/MapCard.vue";
export default {
<<<<<<< HEAD
  props: [
    "id_visitor",
    "id",
    "fname",
    "lname",
    "tel",
    "category",
    "room",
    "contract",
  ],
  components: {
    MapCard,
=======
   props: ['id_visitor','id','fname','lname','tel','category','room','contract'],
   components: {
    MapCard
>>>>>>> 059f54e8d7f6c5a8a86ce481a28b1af5ab67a28a
  },
};
</script>

<style>
.tag {
  width: 50px;
}
.blink {
  animation: blinker 5s linear infinite;
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}
</style>