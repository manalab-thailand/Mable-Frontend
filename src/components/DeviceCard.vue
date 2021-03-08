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
          <div class="text-h6">Tag #{{ tagdata.tag_id }}</div>
          <div class="text-subtitle2"><q-badge color="green-8" label="1202A" /></div>
          
        </div>

        <div class="col-auto">
          <q-btn color="primary" round flat icon="more_vert">
            <q-menu cover auto-close>
              <q-list>
                <q-item clickable>
                  <q-item-section>View detail</q-item-section>
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
            <q-item-label>{{ tagdata.first_name + ' ' + tagdata.last_name}}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Telno</q-item-label>
            <q-item-label>{{ tagdata.tel }}</q-item-label>
          </q-item-section>
        </q-item>
        <q-item v-ripple>
          <q-item-section>
            <q-item-label overline>Tag ID</q-item-label>
            <q-item-label>{{ tagdata.tag_address }}</q-item-label>
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
  </q-card>
</template>

<script>
export default {
  props: ["tagdata"],
};
</script>

<style>
</style>