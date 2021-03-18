<template>
   <q-page class="q-pa-sm">
    <section-header
      title="Register"
      subTitle="การลงทะเบียน Tag"
    ></section-header>
    <div class="row q-gutter-col-md  justify-center">
      <div class="col-9">
        <q-card class="my-card bg-indigo-1 rounded-borders-20 shadow-20 q-ma-sm">
    <q-card-section class="text-primary">
      <div class="row items-center no-wrap">
        <div class="col-3">
        <div class="text-center">
        <q-avatar square size="150px">
          <q-icon name="fas fa-user-tag" color="orange-8" />
        </q-avatar>
      </div>    
        </div>  
        <div class="col-7">
          <div class="text-h3">Tag 2</div>
          <div class="text-subtitle2"><q-badge color="red-8" label="Disconnected" /></div>
          
        </div>
      </div>
    </q-card-section>
    <q-card-section style="margin:30px">
      <div class="row">
        <div class="col-2">
          Name
        </div>
        <div class="col-4">
          <q-input v-model="Fname" label="Fist Name" />
        </div>
        <div class="col-4">
          <q-input v-model="Lname" label="Last Name" />
        </div>
      </div>
      <div class="row" id="top">
        <div class="col-2">
          Phone
        </div>
        <div class="col-8">
          <q-input v-model="Phone" label="Number Phone" />
        </div>
      </div>
      <div class="row" id="top">
        <div class="col-2">
          ID civilizecation
        </div>
        <div class="col-8">
          <q-input v-model="ID" label="13 ID Civilication" />
        </div>
      </div>
      <div class="row" id="top">
        <div class="col-2">
          Person Contract
        </div>
        <div class="col-8">
          <q-input v-model="Preson" label="Person Contract" />
        </div>
      </div>
      <div class="row" id="top">
        <div class="col-2">
          Type
        </div>
        <div class="col-8">
          <q-input v-model="Type" label="Type to contract" />
        </div>
      </div>
      <div class="row" id="top">
        <div class="col-2">
          Location
        </div>
        <div class="col-8">
          <q-input v-model="Location" label="Location to contract" />
        </div>
      </div>
      <div class="row justify-end" id="topper">
        <div class="col-3">
          <q-btn color="primary-gradient" icon="check" to="/index" label="OK" clickable />
        </div>
      </div>
    </q-card-section>
  </q-card>
      </div>
    
    </div>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import DeviceCard from "../components/DeviceCard.vue"
import AddCard from "../components/AddCard.vue";
export default {
  name: "PageIndex",
  components: {
    SectionHeader,
    DeviceCard,
    AddCard
  },
  data () {
    return {
      Fname: '',
      Lname: '',
      Phone: '',
      ID: '',
      Location: '',
      Type: '',
      Preson:'',
    }


}
}
</script>

<style>
#top{
  margin-top: 10px;
}
#topper{
  margin-top: 50px;
  margin-bottom: 30px;
}
</style>