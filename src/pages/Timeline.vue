<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Time Line"
      subTitle="แสดงข้อมูลการใช้งานของ User"
    ></section-header>
    <div class="row justify-evenly">
      <div v-for="itemz in list" :key="itemz.visitor_id">
        <div v-if="itemz.visitor_id == id">
          <info-card
            :fname="itemz.first_name"
            :lname="itemz.last_name"
            :tel="itemz.tel"
            :id_civiliz="itemz.id_civiliz"
            :category="itemz.category"
          />
        </div>
      </div>
      <q-card class="col-3 rounded-borders-10 shadow-5" id="my-card-2">
        <q-icon
          color="blue"
          id="icon"
          class="center"
          name="fas fa-map-marked"
        />
        <q-card-section class="text-h4 text-center">
          <div>Tag {{ this.id }}</div>
        </q-card-section>
      </q-card>
    </div>
    <q-timeline color="secondary" style="padding: 2rem">
      <q-timeline-entry heading> Timeline </q-timeline-entry>
      
      <q-timeline-entry v-for="time in timeline" :key="time.time" :title="time.room" :subtitle="time.date">
        Time : {{time.time}}
      </q-timeline-entry>
      <q-timeline-entry title=" Start " subtitle=" "  icon="watch_later">
      </q-timeline-entry>
    </q-timeline>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import InfoCard from "../components/InfoCard.vue";
import { axios } from "boot/axios";
const moment = require("moment");
export default {
  components: {
    SectionHeader,
    InfoCard,
  },

  data() {
    return {
      id: this.$route.params.id,
      timeline: [],
      list: undefined,
      list2: undefined,
      array: [
        { id: "button1", count: { count1: "kan1", count2: "kan2" } },
        { id: "button2", count: { count1: "kan1", count2: "kan2" } },
        { id: "button3", count: { count1: "kan1", count2: "kan2" } },
      ],
    };
  },
  async mounted() {
    let resp = await axios.get("http://localhost:3030/api/visitors");
    this.list = resp.data.result.rows;
    console.warn("list item visitors");
    console.warn(this.list);

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

    console.warn(this.array[0].count.count1);
    for (var i = 0; i < this.list2.length; i++) {
      if (this.id == this.list2[i].visitor_id) {
        console.warn("time start : " + this.list2[i].time_start);
        console.warn("time stop : " + this.list2[i].time_stop);
        for (var j = 0; j < this.list4.length; j++) {
          if (
            this.list2[i].time_start <= this.list4[j].scan_timestamp &&
            this.list2[i].time_stop >= this.list4[j].scan_timestamp &&
            this.list2[i].tag_address == this.list4[j].device_address
          ) {
            console.warn(
              moment(this.list4[j].scan_timestamp).format("YYYY-MM-DD hh:mm:ss")
            );
            for (var k = 0; k < this.list3.length; k++) {
              if (
                this.list4[j].device_address == this.list3[k].scanner_address
              ) {
                const newItem = {
                  time_spam: moment(this.list4[j].scan_timestamp).format(
                    "YYYY-MM-DD hh:mm"
                  ),
                  room : 102,
                };
                this.timeline.push(newItem);
              }
            }
          } else if (
            this.list2[i].time_start <= this.list4[j].scan_timestamp &&
            this.list2[i].time_stop == null &&
            this.list2[i].tag_address == this.list4[j].device_address
          ) {
            console.warn(
              moment(this.list4[j].scan_timestamp).format("YYYY-MM-DD hh:mm")
            );
           for (var k = 0; k < this.list3.length; k++) {
              if (
                this.list4[j].scanner_id == this.list3[k].scanner_address
              ) {
                const newItem = {
                  time: moment(this.list4[j].scan_timestamp).format(
                    "hh:mm"
                  ),
                  date: "Date : "+moment(this.list4[j].scan_timestamp).format(
                    "DD - MM - YYYY"
                  ),
                  room : "Room : "+this.list3[k].room,
                };
                this.timeline.push(newItem);
              }
            }
          }
        }
      }
    }
    console.warn(this.timeline);
  },
};
</script>

<style lang="sass" scoped>
#my-card-1
  height: 100%
  padding: 24px
#my-card-2
  padding: 30px
  height: 100%
#icon
  font-size: 7em
  display: inline-block
  width: 100%
</style>
