<template>
  <div>
    <q-tabs v-model="tab" class="tab-zone text-info" b>
      <q-tab name="Dairy" label="Dairy" />
      <q-tab name="Weekly" label="Weekly" />
      <q-tab name="Monthly" label="Monthly" />
    </q-tabs>
    <div class="q-pa-md">
      <q-table title="Timeline" :data="data" :columns="columns" row-key="name">
        <template v-slot:header="props">
          <q-tr :props="props">
            <q-th auto-width />
            <q-th v-for="col in props.cols" :key="col.name" :props="props">
              {{ col.label }}
            </q-th>
          </q-tr>
        </template>

        <template v-slot:body="props">
          <q-tr :props="props">
            <q-td auto-width>
              <q-btn
                size="md"
                color="primary"
                round
                to="/timeline"
               :icon="props.expand ? '':'person_pin_circle'"
              />
            </q-td>
            <q-td v-for="col in props.cols" :key="col.name" :props="props">
              {{ col.value }}
            </q-td>
          </q-tr>
        </template>
      </q-table>
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
        {
          name: 'time-stop',
          align: 'center',
          label: 'Time Stop',
          field: 'timeStop',
          sortable: true
        },
        { name: 'type', align: 'center', label: 'Type', field: 'type', sortable: true },
        {
          name: 'location',
          align: 'center',
          label: 'Location',
          field: 'location',
          sortable: true
        }
        // {
        //   name: 'timeline',
        //   label: 'Timeline',
        //   field: 'timeline',
        //   sortable: true
        // }
      ],

      data: [
        {
          name: 'Harry Home',
          timeStart: '8.30',
          timeStop: '11.00',
          type: 'Home',
          location: '1202A'
          // timeline: 11
        },
        {
          name: 'Oliver Home',
          timeStart: '11.30',
          timeStop: '13.20',
          type: 'Home',
          location: '1202A'
          // timeline: 54
        },
        {
          name: 'Jack Home',
          timeStart: '14.30',
          timeStop: '15.00',
          type: 'Home',
          location: '1302A'
          // timeline: 54
        },
        {
          name: 'Alfie Home',
          timeStart: '15.28',
          timeStop: '16.30',
          type: 'Home',
          location: '1402A'
          // timeline: 54
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
