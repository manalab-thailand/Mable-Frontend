<template>
  <div id="user-offline">
    <q-card class="my-card bg-warning">
      <q-card-section class="text-center">
        <q-icon color="negative" name="fas fa-tag" />
      </q-card-section>
      <q-card-section>
        <div class="row items-center no-wrap text-center">
          <div class="col text-white">
            <div class="text-h5">{{userData[0].id}}</div>
            <div class="text-h6">{{userData[0].status}}</div>
          </div>
        </div>
      </q-card-section>

      <q-card-section class="bg-info">
        <p>name: {{userData[0].name}}</p>
        <p>tel: {{userData[0].tel}}</p>
        <p>type: {{userData[0].type}}</p>
        <p>location: {{userData[0].location}}</p>
      </q-card-section>

      <q-separator />

      <q-card-actions class="">
        <q-btn flat class="text-white">...</q-btn>
      </q-card-actions>
    </q-card>
  </div>
</template>

<script>
const userData = [
  {
    id: 2,
    name: 'Mr.Banana',
    tel: '0215423154',
    type: 'Silver Bluggoe',
    location: '1202A',
    status: 'Offline'
  }
]
export default {
  name: 'user-offline',
  data () { return { userData } }
}

</script>

<style lang="sass" scoped></style>
