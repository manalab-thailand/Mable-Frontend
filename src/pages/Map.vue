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
      <div class="hall">
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
      </div>
      <div class="tranning">
        <div class="row"></div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
          <div class="col"><icon-map></icon-map></div>
        </div>
        <div class="row">
          <div class="col"><icon-map></icon-map></div>
        </div>
      </div>
      <div class="hall102">
        <div class="row"></div>
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
    </div>
  </q-page>
</template>

<script>
import IconMap from "src/components/IconMap.vue";
import SectionHeader from "../components/SectionHeader.vue";
export default {
  components: {
    SectionHeader,
    IconMap,
  },
};
</script>

<style>
img {
  width: 65%;
  display: block;
  margin: 0 auto;
}
.hall {
  position: absolute;
  top: 35%;
  left: 37%;
}
.tranning {
  position: absolute;
  top: 52%;
  left: 66%;
}
.hall102 {
  position: absolute;
  top: 56%;
  left: 50.5%;
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