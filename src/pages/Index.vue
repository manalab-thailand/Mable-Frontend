<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <add-card></add-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
      
    </div>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import DeviceCard from "../components/DeviceCard.vue"
import AddCard from "../components/AddCard.vue";
export default {
  name: "PageIndex",
  components: {
    SectionHeader,
    DeviceCard,
    AddCard
  },
};
</script>
