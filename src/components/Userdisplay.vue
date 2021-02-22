<template>
  <div id="user-display">
    <q-card class="my-card bg-warning">
      <q-card-section class="text-center">
        <q-icon color="secondary" name="fas fa-tag" />
        <q-btn flat class="text-white">...</q-btn>
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
        <p>name: {{ userData[0].name }}</p>
        <p>tel: {{ userData[0].tel}}</p>
        <p>type: {{ userData[0].type }}</p>
        <p>location: {{ userData[0].location }}</p>
      </q-card-section>

    </q-card>
  </div>
</template>

<script>
const userData = [
  {
    id: 1,
    name: 'Mr.Apple',
    tel: '0921624517',
    type: 'Winter banana',
    location: '1202A',
    status: 'Online'
  }
]
export default {
  name: 'user-display',
  props: {
    UserData: Array
  },
  data () {
    return {
      userData
    }
  }
}
</script>

<style lang="sass" scoped>

</style>
