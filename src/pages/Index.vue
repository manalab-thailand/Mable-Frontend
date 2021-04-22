<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div v-for="items in list2" class="col-2" :key="items.taguse_id">
        <add-card v-if="items.visitor_id == 0" :id="items.taguse_id"></add-card>
        <div v-for="item in list" :key="item.visitor_id">
          <device-card
            class="col-4"
            v-if="item.visitor_id == items.visitor_id"
            :id="items.taguse_id"
            :fname="item.first_name"
            :lname="item.last_name"
            :tel="item.tel"
            :category="item.category"
            :location ="items.tag_address"
          ></device-card>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import DeviceCard from "../components/DeviceCard.vue";
import AddCard from "../components/AddCard.vue";
import { axios } from "boot/axios";
const moment = require("moment");

export default {
  name: "PageIndex",
  components: {
    SectionHeader,
    DeviceCard,
    AddCard,
  },
  data() {
    return { list: undefined, list2: undefined };
  },
  async mounted() {

    let resp = await axios.get("http://localhost:3030/api/visitors");
    this.list = resp.data.result.rows;
    console.warn(this.list);
    

    let resp2 = await axios.get("http://localhost:3030/api/taguse");
    this.list2 = resp2.data.result.rows;
    console.warn(this.list2);

    let resp3 = await axios.get("http://localhost:3030/api/scanner");
    this.list3 = resp3.data.result.rows;
    console.warn(this.list3);

    let resp4 = await axios.get("http://localhost:3030/api/locations");
    this.list4 = resp4.data.result.rows;
    console.warn(this.list4);

    // console.warn(moment().locale("th").format("hh:mm"));
  },
};
</script>
