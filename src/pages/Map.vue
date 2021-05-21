<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Map"
      subTitle="แสดง Tag ติดตาม ณ เวลาปัจจุบัน"
    ></section-header>
    <div class="row">
      <div class="col q-ma-md">
        <div class="text-h4 text-primary" style="margin-left: 30px">
          Floor 1
        </div>
      </div>
    </div>
    <div class="container">
      <q-img class="profile-image" src="~assets/map_1.jpg" native-context-menu>
      </q-img>
      <!--------------------------- Location Hall -----------------------------------> 
      <div class="hall-1">
        <div class="row">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.location == 'Hell'"
                class="col"
              >
                <icon-map
                  :id_visitor="item.visitor_id"
                  :id="item.id"
                  :fname="item.fname"
                  :lname="item.lname"
                  :tel="item.tel"
                  :category="item.category"
                  :room="item.location"
                ></icon-map>
              </div>
            </div>
        </div>
      </div>
      <!--------------------------- Location Room 103 -----------------------------------> 
      <div class="room-103">
        <div class="col">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.location == 103"
                class="col"
              >
                <icon-map
                  :id_visitor="item.visitor_id"
                  :id="item.id"
                  :fname="item.fname"
                  :lname="item.lname"
                  :tel="item.tel"
                  :category="item.category"
                  :room="item.location"
                ></icon-map>
              </div>
            </div>
        </div>
      </div>
      <!--------------------------- Location Room 105 -----------------------------------> 
      <div class="room-105">
        <div class="col">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.location == 105"
                class="col"
              >
                <icon-map
                  :id_visitor="item.visitor_id"
                  :id="item.id"
                  :fname="item.fname"
                  :lname="item.lname"
                  :tel="item.tel"
                  :category="item.category"
                  :room="item.location"
                ></icon-map>
              </div>
            </div>
        </div>
      </div>
      <!--------------------------- Location Room 107 -----------------------------------> 
      <div class="room-107">
        <div class="row">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.location == 107"
                class="col"
              >
                <icon-map
                  :id_visitor="item.visitor_id"
                  :id="item.id"
                  :fname="item.fname"
                  :lname="item.lname"
                  :tel="item.tel"
                  :category="item.category"
                  :room="item.location"
                ></icon-map>
              </div>
            </div>
        </div>
      </div>
      <!--------------------------- Location Room 102 -----------------------------------> 
      <div class="room-102">
        <div class="row">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.location == 102"
                class="col"
              >
                <icon-map
                  :id_visitor="item.visitor_id"
                  :id="item.id"
                  :fname="item.fname"
                  :lname="item.lname"
                  :tel="item.tel"
                  :category="item.category"
                  :room="item.location"
                ></icon-map>
              </div>
            </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import IconMap from "src/components/IconMap.vue";
import SectionHeader from "../components/SectionHeader.vue";

import { axios } from "boot/axios";

export default {
  components: {
    SectionHeader,
    IconMap,
  },
  data() {
    return {
      dashbord: [],
    };
  },
  async mounted() {
    //<------------------------- Connect Database ----------------------------------->
    let resp = await axios.get("http://localhost:3030/api/visitors");
    this.list = resp.data.result.rows;
    console.warn("list item visitors");
    console.warn(this.list);

    let resp2 = await axios.get("http://localhost:3030/api/scanlog");
    this.list2 = resp2.data.result.rows;
    console.warn("list2 scanerlog");
    console.warn(this.list2);
    //<-------------------------Create Dashbord ----------------------------------->
    for (var i = 0; i < this.list.length; i++) {
      if (this.list[i].time_stop == null) {
        for (var j = 0; j < this.list2.length; j++) {
          if (this.list[i].tag_address == this.list2[j].device_address) {
            const newItem = {
              id: this.list[i].tag_id,
              fname: this.list[i].first_name,
              lname: this.list[i].last_name,
              tel: this.list[i].tel,
              contract: this.list[i].contract,
              category: this.list[i].category,
              location: this.list2[j].room,
              visitor_id: this.list[i].visitor_id,
            };
            this.dashbord.push(newItem);
            break;
          }
        }
      }
    }
    console.warn(this.dashbord);
  },
};
</script>

<style>
img {
  width: 65%;
  display: block;
  margin: 0 auto;
}
.hall-1 {
  position: absolute;
  top: 35%;
  left: 37%;
}
.room-102 {
  position: absolute;
  top: 56%;
  left: 50.5%;
}
.room-103 {
  position: absolute;
  top: 15%;
  left: 59%;
}
.room-105 {
  position: absolute;
  top: 19%;
  left: 64%;
}
.room-107 {
  position: absolute;
  top: 21%;
  left: 68.3%;
}
.container {
  position: relative;
}
</style>
