<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div v-for="items in list2" class="col-2" :key="items.taguse_id">
        <add-card v-if="items.visitor_id == 0" :id="items.taguse_id"></add-card>
        <div v-for="item in dashbord" :key="item.id">
          <device-card
            class="col-4"
            v-if="item.id == items.taguse_id"
            :id="items.taguse_id"
            :fname="item.fname"
            :lname="item.lname"
            :tel="item.tel"
            :contract="item.contract"
            :category="item.category"
            :location="item.location"
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
    return {
      dashbord: [],
      list: undefined,
      list2: undefined,
      list3: undefined,
      list4: undefined,
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

    console.log(this.list[0].first_name);
    for (var i = 0; i < this.list2.length; i++) {
      for (var j = 0; j < this.list.length; j++) {
        if (this.list2[i].visitor_id == this.list[j].visitor_id) {
          // console.warn(
          //   "I : " + this.list2[i].taguse_id + " j :" + this.list[j].visitor_id
          // );
          // console.warn("id : " + this.list2[i].taguse_id);
          // console.warn(
          //   "Name " + this.list[j].first_name + " " + this.list[j].last_name + i
          // );
          // console.warn("tel : " + this.list[j].tel);
          // console.warn("category : " + this.list[j].category);
          // console.warn("contract : " + this.list[j].contract);
          // console.warn("id_civiliz : " + this.list[j].id_civiliz);
          // console.warn("tag_address : " + this.list2[i].tag_address);
          // console.warn("tag_address(log) : " + this.list4[i].device_address);
          // console.warn("scanner_id(log) : " + this.list4[i].scanner_id);
          for (var k = 0; k < this.list3.length; k++) {
            if (this.list4[i].scanner_id == this.list3[k].scanner_address) {
              // console.warn("room : " + this.list3[k].room);
              const newItem = {
                id: this.list2[i].taguse_id,
                fname:this.list[j].first_name,
                lname:this.list[j].last_name,
                tel:this.list[j].tel,
                contract:this.list[j].contract,
                category:this.list[j].category,
                location: this.list3[k].room,
                visitor_id: this.list[j].visitor_id,
              };
              this.dashbord.push(newItem);
            }
          }
        }
      }
    }
    console.warn(this.dashbord);
  },
};
</script>
