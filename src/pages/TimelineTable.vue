<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Report"
      subTitle="แสดงข้อมูลการใช้งานของ Users"
    ></section-header>
    <q-tabs v-model="tab" class="q-mb-lg">
      <q-tab class="text-purple" name="Dairy" label="Dairy"  />
      <q-tab
        class="text-orange"
        name="Monthly"
        label="Monthly"
      />
      <q-tab class="text-teal" name="Select Date" label="Select Date" />
    </q-tabs>

    <q-tab-panels
      v-model="tab"
      animated
      transition-prev="fade"
      transition-next="fade"
      style="background-color: #eceff1"
    >
      <!-- ============================================================================================================================== -->
      <q-tab-panel name="Dairy">
        <div class="q-pa-md">
          <q-table
            title="Timeline - Dairy 13/01/2021"
            :data="list_day"
            :columns="columns"
            row-key="name"
            class="rounded-borders-10 shadow-5"
          >
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
                    color="primary-gradient"
                    round
                    :to="'/timeline/' + props.row.id"
                    :icon="props.expand ? '' : 'person_pin_circle'"
                  />
                </q-td>
                <q-td v-for="col in props.cols" :key="col.name" :props="props">
                  {{ col.value }}
                </q-td>
              </q-tr>
            </template>
          </q-table>
        </div>
      </q-tab-panel>
      <!-- ================================================================================================================== -->
      <q-tab-panel name="Monthly">
        <div class="q-pa-md">
          <q-table
            title="Timeline - Monthry 02/2021"
            :data="list_month"
            :columns="columns"
            row-key="name"
            class="rounded-borders-10 shadow-5"
          >
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
                    color="primary-gradient"
                    round
                    :to="'/timeline/' + props.row.id"
                    :icon="props.expand ? '' : 'person_pin_circle'"
                  />
                </q-td>
                <q-td v-for="col in props.cols" :key="col.name" :props="props">
                  {{ col.value }}
                </q-td>
              </q-tr>
            </template>
          </q-table>
        </div>
      </q-tab-panel>
      <!-- ================================================================================================================================= -->
      <q-tab-panel name="Select Date">
        <div class="row">
          <div class="row-4">Select Date</div>
          <div class="q-pa-md" style="max-width: 300px">
            <q-input filled v-model="date" mask="date" :rules="['date']">
              <template v-slot:append>
                <q-icon name="event" class="cursor-pointer">
                  <q-popup-proxy
                    ref="qDateProxy"
                    transition-show="scale"
                    transition-hide="scale"
                  >
                    <q-date v-model="date">
                      <div class="row items-center justify-end">
                        <q-btn
                          v-close-popup
                          label="Close"
                          color="primary"
                          @click="select()"
                          flat
                        />
                      </div>
                    </q-date>
                  </q-popup-proxy>
                </q-icon>
              </template>
            </q-input>
          </div>
        </div>

        <div class="q-pa-md">
          <q-table
            title="Timeline"
            :data="list_select"
            :columns="columns"
            row-key="name"
            class="rounded-borders-10 shadow-5"
          >
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
                    color="primary-gradient"
                    round
                    :id="0"
                    to="/timeline"
                    :icon="props.expand ? '' : 'person_pin_circle'"
                  />
                </q-td>
                <q-td v-for="col in props.cols" :key="col.name" :props="props">
                  {{ col.value }}
                </q-td>
              </q-tr>
            </template>
          </q-table>
        </div>
      </q-tab-panel>
    </q-tab-panels>
  </q-page>
</template>
// =========================================================================================================================================
<script>
import SectionHeader from "../components/SectionHeader.vue";
const moment = require("moment");
import { axios } from "boot/axios";

export default {
  components: {
    SectionHeader,
  },
  data() {
    return {
      tab: "Dairy",
      date: "2021/03/18",
      list: undefined,
      list5: undefined,
      list_month: [],
      list_day: [],
      list_select: [],
      dashbord: [],
      text: "",
      columns: [
        {
          name: "name",
          required: true,
          label: "Name",
          align: "left",
          field: (row) => row.name,
          format: (val) => `${val}`,
          sortable: true,
        },
        {
          name: "date",
          align: "center",
          label: "Date",
          field: "date",
          sortable: true,
        },
        {
          name: "time-start",
          align: "center",
          label: "Time Start",
          field: "time_start",
          sortable: true,
        },
        {
          name: "time-stop",
          align: "center",
          label: "Time Stop",
          field: "time_stop",
          sortable: true,
        },
        {
          name: "type",
          align: "center",
          label: "Type",
          field: "type",
          sortable: true,
        },
        {
          name: "location",
          align: "center",
          label: "Location",
          field: "location",
          sortable: true,
        },
      ],
    };
  },
  async mounted() {
    let resp = await axios.get("http://localhost:3030/api/visitors");
    this.list = resp.data.result.rows;
    console.warn("Visitor ");
    console.warn(resp.data.result.rows);

    let resp2 = await axios.get("http://localhost:3030/api/taguse");
    this.list2 = resp2.data.result.rows;
    console.warn("list2 items taguse");
    console.warn(this.list2);

    let resp3 = await axios.get("http://localhost:3030/api/locations");
    this.list3 = resp3.data.result.rows;
    console.warn("list3 location");
    console.warn(this.list3);

    let resp4 = await axios.get("http://localhost:3030/api/scanlog");
    this.list4 = resp4.data.result.rows;
    console.warn("list4 scanerlog");
    console.warn(this.list4);

    console.log(this.list[0].first_name);
    for (var i = 0; i < this.list2.length; i++) {
      for (var j = 0; j < this.list.length; j++) {
        if (this.list2[i].visitor_id == this.list[j].visitor_id) {
          for (var k = 0; k < this.list4.length; k++) {
            if (
              this.list2[i].tag_address == this.list4[k].device_address &&
              moment(this.list2[i].time_stop).format("YYYY-MM-DD hh:mm") ==
                moment(this.list4[k].scan_timestamp).format("YYYY-MM-DD hh:mm")
            ) {
              for (var l = 0; l < this.list3.length; l++) {
                if (this.list4[k].scanner_id == this.list3[l].scanner_address) {
                  const newItem = {
                    id: this.list2[i].visitor_id,
                    date: moment(this.list2[i].time_start).format("YYYY-MM-DD"),
                    location: this.list3[l].room,
                    name:
                      this.list[j].first_name + " " + this.list[j].last_name,
                    time_start: moment(this.list2[i].time_start).format(
                      "hh:mm"
                    ),
                    time_stop: moment(this.list2[i].time_stop).format("hh:mm"),
                    type: this.list[j].category,
                  };
                  this.dashbord.push(newItem);
                }
              }
            }
            if (
              this.list2[i].tag_address == this.list4[k].device_address &&
              this.list2[i].time_stop == null
            ) {
              for (var l = 0; l < this.list3.length; l++) {
                if (this.list4[k].scanner_id == this.list3[l].scanner_address) {
                  const newItem = {
                    id: this.list2[i].visitor_id,
                    date: moment(this.list2[i].time_start).format("YYYY-MM-DD"),
                    location: this.list3[l].room,
                    name:
                      this.list[j].first_name + " " + this.list[j].last_name,
                    time_start: moment(this.list2[i].time_start).format(
                      "hh:mm"
                    ),
                    time_stop: "In Use",
                    type: this.list[j].category,
                  };
                  this.dashbord.push(newItem);
                }
              }
              break;
            }
          }
        }
      }
    }
    console.warn(this.dashbord);
     for (var i = 0; i < this.dashbord.length; i++) {
        if (moment(this.dashbord[i].date).format("YYYY-MM") == "2021-01") {
          const newItems = {
            id: this.dashbord[i].id,
            date: this.dashbord[i].date,
            location: this.dashbord[i].location,
            name: this.dashbord[i].name,
            time_start: this.dashbord[i].time_start,
            time_stop: this.dashbord[i].time_stop,
            type: this.dashbord[i].type,
          };
          this.list_month.push(newItems);
        }
        
      }
      console.warn(this.list_month);
       for (var i = 0; i < this.dashbord.length; i++) {
        if (moment(this.dashbord[i].date).format("YYYY-MM-DD") == "2021-02-13") {
          const newItems = {
            id: this.dashbord[i].id,
            date: this.dashbord[i].date,
            location: this.dashbord[i].location,
            name: this.dashbord[i].name,
            time_start: this.dashbord[i].time_start,
            time_stop: this.dashbord[i].time_stop,
            type: this.dashbord[i].type,
          };
          this.list_day.push(newItems);
        }
        
      }
      console.warn(this.list_day);
       this.list_select = this.dashbord
      console.warn(this.list_select);
      
  },
  methods: {
    async select() {
      console.warn(this.date)
     this.list_select = []
     for (var i = 0; i < this.dashbord.length; i++) {
        if (moment(this.dashbord[i].date).format("YYYY/MM/DD") == this.date) {
          const newItems = {
            id: this.dashbord[i].id,
            date: this.dashbord[i].date,
            location: this.dashbord[i].location,
            name: this.dashbord[i].name,
            time_start: this.dashbord[i].time_start,
            time_stop: this.dashbord[i].time_stop,
            type: this.dashbord[i].type,
          };
          this.list_select.push(newItems);
        }
        
      }
      console.warn(this.list_select);
    },
  },
};
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
