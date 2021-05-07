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

      <div class="hall-1">
        <div class="row">
          <div v-for="items in list2" class="col-2" :key="items.taguse_id">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.id == items.taguse_id && item.location == 'Hall'"
                class="col"
              >
                <icon-map
                  :id_visitor="items.visitor_id"
                  :id="items.taguse_id"
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
      <div class="room-103">
        <div class="col">
          <div v-for="items in list2" class="col-2" :key="items.taguse_id">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.id == items.taguse_id && item.location == 103"
                class="col"
              >
                <icon-map
                  :id_visitor="items.visitor_id"
                  :id="items.taguse_id"
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
      <div class="room-105">
        <div class="col">
          <div v-for="items in list2" class="col-2" :key="items.taguse_id">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.id == items.taguse_id && item.location == 105"
                class="col"
              >
                <icon-map
                  :id_visitor="items.visitor_id"
                  :id="items.taguse_id"
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
      <div class="room-107">
        <div class="row">
          <div v-for="items in list2" class="col-2" :key="items.taguse_id">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.id == items.taguse_id && item.location == 107"
                class="col"
              >
                <icon-map
                  :id_visitor="items.visitor_id"
                  :id="items.taguse_id"
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
      <div class="room-102">
        <div class="row">
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in dashbord" :key="item.id">
              <div
                v-if="item.id == items.taguse_id && item.location == 102"
                class="col"
              >
                <icon-map 
                  :id_visitor="items.visitor_id"
                  :id="items.taguse_id"
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
       <!-- <div class="hall-1">
          <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div> 
      <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
      </div>
       <div class="room-103">
        <div class="col">
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
        </div>
      </div>
      <div class="room-105">
        <div class="col">
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
        </div>
      </div>
      <div class="room-107">
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
      </div>
      <div class="room-102">
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
      </div> -->
    </div>
    <p></p>
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
      list: undefined,
      list2: undefined,
      list3: undefined,
      list4: undefined,
      dashbord: [],
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
        if (
          this.list2[i].visitor_id == this.list[j].visitor_id &&
          this.list2[i].time_stop == null
        ) {
          console.warn(this.list2[i].visitor_id);
          for (var l = 0; l < this.list4.length; l++) {
            if (this.list2[i].tag_address == this.list4[l].device_address) {
              console.warn(this.list2[i].tag_address);
              for (var k = 0; k < this.list3.length; k++) {
                if (this.list4[l].scanner_id == this.list3[k].scanner_address) {
                  const newItem = {
                    id: this.list2[i].taguse_id,
                    fname: this.list[j].first_name,
                    lname: this.list[j].last_name,
                    tel: this.list[j].tel,
                    contract: this.list[j].contract,
                    category: this.list[j].category,
                    location: this.list3[k].room,
                    visitor_id: this.list[j].visitor_id,
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

//  <div class="row" style="hight:800px;width:300px;top: 280px; left: 545px;">
//       <div style="width:40px">
//         <icon-map></icon-map>
//       </div>
//       <div style="width:40px">
//         <icon-map></icon-map>
//       </div>
      
//     </div>