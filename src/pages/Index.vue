<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div class="col-md-2 col-12" v-for="tag in tags" :key="tag.tag_id">
        {{ tag.tag_address }}
        <device-card :tagdata="tag"></device-card>
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

  async mounted(){
    console.log('state => mounted');
    // Call api get all tag data
    const url = 'http://mean.psu.ac.th:3000/api/data';
    const result = await this.$axios.get(url); 
    const tags = result.data.result.rows;
    console.log(tags);
    this.tags = tags;
  },
  data(){
    return {
      tags : []
    }
  }
  
};
</script>
