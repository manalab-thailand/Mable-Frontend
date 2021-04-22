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
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in list" :key="item.visitor_id">
              <div
                v-if="
                  item.visitor_id == items.visitor_id && items.location_id == 3
                "
                class="col"
              >
                <icon-map
                :id_visitor="items.visitor_id"
                :id="items.taguse_id"
                :fname="item.first_name"
                :lname="item.last_name"
                :tel="item.tel"
                :category="item.category"
                :room="'Hall'"
                ></icon-map>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="room-103">
        <div class="col">
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in list" :key="item.visitor_id">
              <div
                v-if="
                  item.visitor_id == items.visitor_id && items.location_id == 3
                "
                class="col"
              >
                <icon-map
                :id_visitor="items.visitor_id"
                :id="items.taguse_id"
                :fname="item.first_name"
                :lname="item.last_name"
                :tel="item.tel"
                :category="item.category"
                :room="'Room 103'"
                ></icon-map>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="room-105">
        <div class="col">
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in list" :key="item.visitor_id">
              <div
                v-if="
                  item.visitor_id == items.visitor_id && items.location_id == 4
                "
                class="row"
              >
                <icon-map
                :id_visitor="items.visitor_id"
                :id="items.taguse_id"
                :fname="item.first_name"
                :lname="item.last_name"
                :tel="item.tel"
                :category="item.category"
                :room="'Room 105'"
                ></icon-map>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="room-107">
        <div class="row">
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in list" :key="item.visitor_id">
              <div
                v-if="
                  item.visitor_id == items.visitor_id && items.location_id == 5
                "
                class="col"
              >
                <icon-map
                :id_visitor="items.visitor_id"
                :id="items.taguse_id"
                :fname="item.first_name"
                :lname="item.last_name"
                :tel="item.tel"
                :category="item.category"
                :room="'Room 107'"
                ></icon-map>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="room-102">
        <div class="row">
          <div v-for="items in list2" :key="items.taguse_id">
            <div v-for="item in list" :key="item.visitor_id">
              <div
                v-if="
                  item.visitor_id == items.visitor_id && items.location_id == 1
                "
                class="col"
              >
                <icon-map
                :id_visitor="items.visitor_id"
                :id="items.taguse_id"
                :fname="item.first_name"
                :lname="item.last_name"
                :tel="item.tel"
                :category="item.category"
                :room="'Room 102'"
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
        </div> -->
      <!-- <div class="row">
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
      <!-- <div class="room-103">
        <div class="col">
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
          <div class="row"><icon-map></icon-map></div>
        </div>
      </div> -->
      <!-- <div class="room-105">
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
    return { list: undefined, list2: undefined, list3: undefined };
  },
  mounted() {
    axios.get("http://localhost:3030/api/visitors").then((resp) => {
      this.list = resp.data.result.rows;
      console.warn(resp.data.result.rows);
    }),
      axios.get("http://localhost:3030/api/locations").then((resp) => {
        this.list3 = resp.data.result.rows;
        console.warn(resp.data.result.rows);
      }),
      axios.get("http://localhost:3030/api/taguse").then((resp) => {
        this.list2 = resp.data.result.rows;
        console.warn(resp.data.result.rows);
      });
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