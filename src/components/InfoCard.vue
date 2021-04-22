<template>
  <q-card class="col-4 rounded-borders-10 shadow-5" id="my-card-1">
        <q-card-section >
        <div class="text-h6">{{fname+' '+lname}}</div>
        <div class="text-subtitle2">Phine : {{ tel }}</div>
        <div class="text-subtitle2">ID civilization : {{id_civiliz}}</div>
      </q-card-section>
       <q-card-section>
        Type : {{category}} <br>
        Location : 1202A<br>
        Contact person : MR.Mavel
      </q-card-section>
      </q-card>
</template>

<script>
export default {
    props: ['fname','lname','tel','category','id_civiliz'],
}
</script>

<style>

</style>