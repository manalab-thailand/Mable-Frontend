<template>
  <q-page class="q-pa-sm">
    <section-header
      title="Time Line"
      subTitle="แสดงข้อมูลการใช้งานของ User"
    ></section-header>
    <div class="row justify-evenly">
      <div v-for="itemz in list" :key="itemz.visitor_id">
        <div v-if="itemz.visitor_id == id">
          <info-card
            :fname="itemz.first_name"
            :lname="itemz.last_name"
            :tel="itemz.tel"
            :id_civiliz="itemz.id_civiliz"
            :category="itemz.category"
          />
        </div>
      </div>
      <q-card class="col-3 rounded-borders-10 shadow-5" id="my-card-2">
        <q-icon
          color="blue"
          id="icon"
          class="center"
          name="fas fa-map-marked"
        />
        <q-card-section class="text-h4 text-center">
          <div>Tag {{ this.id }}</div>
        </q-card-section>
      </q-card>
    </div>
    <q-timeline color="secondary" style="padding: 2rem">
      <q-timeline-entry heading> Timeline </q-timeline-entry>

      <div v-for="items in list2" :key="items.id_history">
        <div v-if="items.id_visitor == id">
          <div v-for="item in list" :key="item.visitor_id">
            <q-timeline-entry v-if="item.visitor_id == id">
              <template v-slot:title>
                {{ items.room + " " + items.id_history }}
              </template>
              <template v-slot:subtitle>
                {{ items.date }}
              </template>
              <div>Time : {{ items.time_start + " - " + items.time_stop }}</div>
            </q-timeline-entry>
          </div>
        </div>
      </div>
    </q-timeline>
  </q-page>
</template>

<script>
import SectionHeader from "../components/SectionHeader.vue";
import InfoCard from "../components/InfoCard.vue";
import { axios } from "boot/axios";
export default {
  components: {
    SectionHeader,
    InfoCard,
  },

  data() {
    return {
      id: this.$route.params.id,
      list: undefined,
      list2: undefined,
    };
  },
  mounted() {
    axios.get("http://localhost:3030/api/visitors").then((resp) => {
      this.list = resp.data.result.rows;
      console.warn(resp.data.result.rows);
    }),
      axios.get("http://localhost:3030/api/history").then((resp) => {
        this.list2 = resp.data.result.rows;
        console.warn(resp.data.result.rows);
        console.warn(this.id);
      });
  },
};
</script>

<style lang="sass" scoped>
#my-card-1
    height: 100%
    padding: 24px
#my-card-2
    padding: 30px
    height: 100%
#icon
    font-size: 7em
    display: inline-block
    width: 100%
</style>
