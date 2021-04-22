<template>
  <q-card class="my-card bg-indigo-1 rounded-borders-20 shadow-20 q-ma-sm">
    <q-card-section class="text-primary">
      <div class="row items-center no-wrap">
        <div class="col">
        <div class="text-center">
        <q-avatar square size="80px">
          <q-icon name="fas fa-user-tag" color="orange-8" />
        </q-avatar>
      </div>    
        </div>  
        <div class="col">
          <div class="text-h6">Guest #{{id}}</div>
          <div class="text-subtitle2"><q-badge color="green-8" label="1202A" /></div>
        </div>

        <div class="col-auto">
          <q-btn color="primary" round flat icon="more_vert">
            <q-menu cover auto-close>
              <q-list>
                <q-item clickable>
                  <q-item-section @click="alert = true">View detail</q-item-section>
                </q-item>
                <q-item clickable to="/map">
                  <q-item-section>Locate on map</q-item-section>
                </q-item>
                <q-item clickable @click="confirm = true">
                  <q-item-section>Return the tag</q-item-section>
                </q-item>
              </q-list>
            </q-menu>
          </q-btn>
        </div>
      </div>
    </q-card-section>

    <q-card-section class="q-pt-none text-primary">
      <q-list separator>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Name</q-item-label>
            <q-item-label>{{fname +' '+lname}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Telno</q-item-label>
            <q-item-label>{{ tel }}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Organization</q-item-label>
            <q-item-label>{{ category}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Contact person</q-item-label>
            <q-item-label>Mr. Teerapong</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-card-section>
    
    <q-dialog v-model="alert">
      <q-card>
        <q-card-section>
          <div class="text-h5">Detail</div>
        </q-card-section>
        <q-card-section class="q-pt-none" style="width: 350px; margin:15px">
          Name : {{fname +' '+lname +' '+location}} <br>
          Tel : {{ tel }}<br>
          ID civilizecation : 19000000000 <br>
          Type : {{ category}}<br>
          Contact Person : Mr.Teerapong<br>
          Location : 1202A
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
    <q-dialog v-model="confirm">
      <q-card>
        <q-card-section class="row items-center">
          <span class="q-ml-sm">Are you sure to resrt.</span>
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="Reset" color="green-6" v-close-popup to="/index"  @click='resetTag()'/>
          <q-btn flat label="Cancel" color="red-8" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </q-card>
  
</template>

<script>
const moment = require('moment');
import { axios } from "boot/axios";
export default {
   props: ['id','fname','lname','tel','category','location'],
  data () {
    return {
      alert: false,
      confirm: false,
    }
  },
  

  
  methods:{
    
    async resetTag(){
      console.log(this.id),
      await axios.put("http://localhost:3030/api/taguse/"+this.id, {
        taguse_id: '"'+this.id+'"',
        time_start: "2021-02-10 15:29:44",
        time_stop: "2021-02-10 15:29:44",
        visitor_id: 0,
        }
        , )
    .then((result)=>{
      console.log(result)
    })
    }
  }
};
</script>

<style>
</style>