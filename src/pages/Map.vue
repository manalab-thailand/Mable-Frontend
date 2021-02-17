<template>
  <div class="q-pa-md">
    <q-btn-dropdown color="primary" label="Select Floor">
      <q-list>
        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Floor 1</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Floor 2</q-item-label>
          </q-item-section>
        </q-item>

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>Floor 3</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-btn-dropdown>
  </div>
</template>

<script>
export default {
  methods: {
    onItemClick () {
      // console.log('Clicked on an Item')
    }
  }
}
</script>

<style lang="scss" scoped>
.mt-center{
    text-align: center;
}
</style>
