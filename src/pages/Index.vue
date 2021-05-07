<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div v-for="item1 in list5" class="col-2" :key="item1.tag_id">
        <div v-for="item in dashbord" :key="item.id">
          <div v-if="item1.tag_address == item.tag_address">
            <div v-if="item.visitor_id != 0">
              <device-card
                class="col-4"
                :id="item.id"
                :fname="item.fname"
                :lname="item.lname"
                :tel="item.tel"
                :contract="item.contract"
                :category="item.category"
                :location="item.location"
                :taguse_id="item.taguse_id"
                :tag_address="item.tag_address"
              ></device-card>
            </div>
            <div v-else>
              <add-card :id="item1.tag_id"></add-card>
            </div>
          </div>
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
      list5: undefined,
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

    let resp5 = await axios.get("http://localhost:3030/api/tags");
    this.list5 = resp5.data.result.rows;
    console.warn("list5 tags");
    console.warn(this.list5);
    for (var i = 0; i < this.list5.length; i++) {
      for (var j = 0; j < this.list2.length; j++) {
        if (
          this.list5[i].tag_address == this.list2[j].tag_address &&
          this.list2[j].time_stop == null
        ) {
          console.warn("kan");
          console.warn(this.list2[j].taguse_id);
          for (var k = 0; k < this.list3.length; k++) {
            if (this.list4[i].scanner_id == this.list3[k].scanner_address) {
              for (var l = 0; l < this.list.length; l++) {
                if (this.list[l].visitor_id == this.list2[j].visitor_id) {
                  const newItem = {
                    id: this.list5[i].tag_id,
                    taguse_id: this.list2[j].taguse_id,
                    fname: this.list[l].first_name,
                    lname: this.list[l].last_name,
                    tel: this.list[l].tel,
                    contract: this.list[l].contract,
                    category: this.list[l].category,
                    location: this.list3[k].room,
                    tag_address: this.list5[i].tag_address,
                    visitor_id: this.list[l].visitor_id,
                  };
                  this.dashbord.push(newItem);
                  console.warn("Tag : "+this.list5[i].tag_id+" id address : "+ this.list5[i].tag_address)
                  break;
                }
              }
            }
          }
          break;
        } else if (
          this.list5[i].tag_address == this.list2[j].tag_address &&
          this.list2[j].time_stop != null
        ) {
          console.warn("kan 1");
          console.warn(this.list2[j].taguse_id);
          const newItem2 = {
            id: this.list5[i].tag_id,
            taguse_id: this.list2[i].taguse_id,
            fname: "",
            lname: "",
            tel: "",
            contract: "",
            category: "",
            location: "",
            tag_address: this.list5[i].tag_address,
            visitor_id: 0,
          };
          this.dashbord.push(newItem2);
          break;
        }
      }
    }
    console.warn(this.dashbord);
  },
};
</script>
