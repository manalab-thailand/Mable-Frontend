<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Time Line"
      subTitle="แสดงข้อมูลการใช้งานของ User"
    ></section-header>
    <!-------------------------- Infomation User ----------------------------------->
    <div v-for="itemz in list" :key="itemz.visitor_id">
      <div v-if="itemz.visitor_id == id" class="row justify-evenly">
        <info-card
          class="col-4"
          :fname="itemz.first_name"
          :lname="itemz.last_name"
          :tel="itemz.tel"
          :id_civiliz="itemz.id_civiliz"
          :category="itemz.category"
          :contract="itemz.contract"
        />
        <q-card class="col-3 rounded-borders-10 shadow-5" id="my-card-2">
          <q-icon
            color="blue"
            id="icon"
            class="center"
            name="fas fa-map-marked"
          />

          <q-card-section class="text-h4 text-center">
            <div>Tag {{ itemz.tag_id }}</div>
          </q-card-section>
        </q-card>
      </div>
    </div>
    <!--------------------------- Timeline User ----------------------------------->
    <q-timeline color="secondary" style="padding: 2rem">
      <q-timeline-entry heading> Timeline </q-timeline-entry>

      <q-timeline-entry
        v-for="time in timeline"
        :key="time.time"
        :title="'Room : ' + time[time.length - 2]"
        :subtitle="time[time.length - 1]"
      >
        Time : {{ time[time.length - 3] }} - {{ time[0] }}
      </q-timeline-entry>
      <q-timeline-entry title=" Start " subtitle=" " icon="watch_later">
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
      time: [],
      list: undefined,
      list2: undefined,
      tag: undefined,
    };
  },
  async mounted() {
    setTimeout(function () {
      location.reload(1);
    }, 60000);
    //<------------------------- Connect Database ---------------------------------------------------หฟกฟหกฟหก----->
    // const url = "http://localhost:3030/api/";
    const url = "http://mean.psu.ac.th:3000/api/";
    let resp1 = await axios.get(url + "visitors");
    this.list = resp1.data.result.rows;
    console.warn("list item visitors");
    console.warn(this.list);

    for (var j = 0; j < this.list.length; j++) {
      if (this.id == this.list[j].visitor_id) {
        break;
      }
    }
    console.warn(" j : " + j);
    let resp2 = await axios.get(url + "selectlog", {
      params: {
        device_address: this.list[j].tag_address,
        time_start: moment(this.list[j].time_start).format(
          "YYYY-MM-DD hh:mm:ss A"
        ),
        time_stop: moment(this.list[j].time_stop).add(1, 'minute').format(
          "YYYY-MM-DD hh:mm:ss A"
        ),
      },
    });
    this.list2 = resp2.data.result.rows;
    console.warn("list2 scanerlog");
    console.warn(this.list2);

    //<------------------------- Create Timeline ----------------------------------->
    var rooms = this.list2[0].room;
    var times = moment(this.list2[0].scan_timestamp).format("hh:mm A")
    console.warn(moment(this.list2[0].scan_timestamp).format("hh:mm A"))
    if (this.list[j].time_stop == null) {
      this.time.push("In Use Now.");
    }
    for (var i = 0; i < this.list2.length; i++) {
      if (this.list2[i].room != rooms 
      // && moment(this.list2[i].scan_timestamp).format("hh:mm A") != times
      ) {
        this.time.push(this.list2[i - 1].room);
        this.time.push(
          moment(this.list2[i].scan_timestamp).format("YYYY-MM-DD")
        );
        this.timeline.push(this.time);
        this.time = [];
        rooms = this.list2[i].room;
        times = moment(this.list2[i].scan_timestamp).format("hh:mm A")
        --i;
      } else {
        this.time.push(moment(this.list2[i].scan_timestamp).format("hh:mm A"));
      }
    }

    this.time.push(this.list2[this.list2.length - 1].room);
    this.time.push(
      moment(this.list2[this.list2.length - 1].scan_timestamp).format(
        "YYYY-MM-DD"
      )
    );

    this.timeline.push(this.time);
    console.warn(this.timeline);
  },
};
</script>

<style lang="sass" scoped>
#my-card-1
  height: 100%
  padding: 27px
#my-card-2
  padding: 30px
  height: 100%
#icon
  font-size: 9em
  display: inline-block
  width: 100%
</style>
