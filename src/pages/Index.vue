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
      <div class="col-md-2 col-12">
        <device-card></device-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader";
import DeviceCard from "../components/DeviceCard"
export default {
  name: "PageIndex",
  components: {
    SectionHeader,
    DeviceCard
  },
};
</script>
