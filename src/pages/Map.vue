<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Map"
      subTitle="แสดง Tag ติดตาม ณ เวลาปัจจุบัน"
    ></section-header>
    <div class="row">
      <div class="col  q-ma-md ">
        <div class="text-h4 text-primary" style=" margin-left: 30px;">Floor 1</div>
      </div>
    </div>
     <img class="profile-image" src="~assets/map_1.jpg" alt="no img">
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
export default {
  components: {
    SectionHeader
  }
}
</script>

<style>
img{
  width: 65%;
    display: block;
    margin: 0 auto;
}

</style>