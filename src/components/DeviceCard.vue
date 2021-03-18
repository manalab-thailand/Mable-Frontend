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
          <div class="text-h6">Guest #1</div>
          <div class="text-subtitle2"><q-badge color="green-8" label="1202A" /></div>
          
        </div>

        <div class="col-auto">
          <q-btn color="primary" round flat icon="more_vert">
            <q-menu cover auto-close>
              <q-list>
                <q-item clickable>
                  <q-item-section @click="alert = true">View detail</q-item-section>
                </q-item>
                <q-item clickable>
                  <q-item-section>Locate on map</q-item-section>
                </q-item>
                <q-item clickable>
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
            <q-item-label>John Doe</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Telno</q-item-label>
            <q-item-label>0899998899</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Organization</q-item-label>
            <q-item-label>Electrician</q-item-label>
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
          Name : John Doe <br>
          Tel : 0899999999<br>
          ID civilizecation : 1900000000000<br>
          Type : Eletecx Mach<br>
          Contact Person : Mr.Teerapong<br>
          Location : 1202A
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </q-card>
  
</template>

<script>
export default {
  props: ["active"],
  data () {
    return {
      alert: false,
      address: ''
    }
  }
};
</script>

<style>
</style>