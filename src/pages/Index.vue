<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Dashboard"
      subTitle="ศูนย์กลางการควบคุม"
    ></section-header>
    <div class="row q-gutter-col-md">
      <div class="col-md-2 col-12">
        <add-card></add-card>
      </div>
      <div v-for="items in list2" v-bind:key="items.visitor_id" >
      <div v-for="item in list" v-bind:key="item.visitor_id" >
        <device-card  v-if='item.visitor_id == items.visitor_id'
          :id='items.taguse_id'
          :fname='item.first_name'
          :lname='item.last_name'
          :tel='item.tel'
          :category='item.category'
        ></device-card>
      </div>
      </div>
      
    </div>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import DeviceCard from "../components/DeviceCard.vue"
import AddCard from "../components/AddCard.vue";
import { axios} from 'boot/axios'

export default {
  name: "PageIndex",
  components: {
    SectionHeader,
    DeviceCard,
    AddCard
  },
  data(){
    return {list:undefined,list2:undefined}
  },
  mounted()
  {
    axios.get('http://mean.psu.ac.th:3000/api/visitors')
    .then((resp)=>{
      this.list=resp.data.result.rows;
      console.warn(resp.data.result.rows);
    }),
    axios.get('http://mean.psu.ac.th:3000/api/taguse')
    .then((resp)=>{
      this.list2=resp.data.result.rows;
      console.warn(resp.data.result.rows);
    })
  
  }
};
</script>
