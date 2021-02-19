<template>
  <div>
    <q-tabs v-model="tab" class="tab-zone">
      <q-tab name="Dairy" label="Dairy"  />
      <q-tab name="Weekly" label="Weekly" />
      <q-tab name="Monthly" label="Monthly" />
    </q-tabs>
     <div class="q-pa-md">
    <q-table
      class="my-sticky-header-table"
      title="Timeline"
      :data="data"
      :columns="columns"
      row-key="name"
      flat
      bordered
    />
  </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tab: 'Dairy',
      columns: [
        {
          name: 'name',
          required: true,
          label: 'Name',
          align: 'left',
          field: row => row.name,
          format: val => `${val}`,
          sortable: true
        },
        {
          name: 'time-start',
          align: 'center',
          label: 'Time Start',
          field: 'timeStart',
          sortable: true
        },
        { name: 'time-stop', label: 'Time Stop', field: 'timeStop', sortable: true },
        { name: 'type', label: 'Type', field: 'type', sortable: true },
        {
          name: 'location',
          label: 'Location',
          field: 'location',
          sortable: true
        },
        {
          name: 'timeline',
          label: 'Limeline',
          field: 'timeline',
          sortable: true
                
        }

      ],

      data: [
        {
          name: 'Harry xxxxx',
          timeStart: '8.30',
          timeStop: '11.00',
          type: 'Xxxxxxxxxx',
          location: '1202A',
          timeline: 87
        },
        {
          name: 'Oliver xxxx',
          timeStart: '11.30',
          timeStop: '13.20',
          type: 'xxxxxx',
          location: '1202A',
          timeline: 54
        },
        {
          name: 'Jack xxxxx',
          timeStart: '14.30',
          timeStop: '15.00',
          type: 'xxxxxxx',
          location: '1302A',
          timeline: 54
        },
        {
          name: 'Alfie xxxxx',
          timeStart: '15.28',
          timeStop: '16.30',
          type: 'xxxxxxx',
          location: '1402A',
          timeline: 54
        }
      ]
    }
  }
}
</script>

<style lang="sass">
.my-sticky-header-table
  /* height or max-height is important */
  height: 490px

  .q-table__top,
  .q-table__bottom,
  thead tr:first-child th
    /* bg color is important for th; just specify one */
    background-color: #c1f4cd

  thead tr th
    position: sticky
    z-index: 1
  thead tr:first-child th
    top: 0

  /* this is when the loading indicator appears */
  &.q-table--loading thead tr:last-child th
    /* height of all previous header rows */
    top: 48px
</style>
