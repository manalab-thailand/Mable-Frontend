      <template>
  <div id="tag-button">
    <q-card class="my-card bg-positive">
      <q-card-section class="card-zone-offine text-center">
       <div class="icon-zone">
             <i class="fas fa-file-alt"></i>
          </div>
        <div class="tag-zone text-center">Report </div>
        <div class="text-subtitle2">Tag1</div>
      </q-card-section>
      <q-card-section class="q-pt-none text-center">
        {{ "Detail" }}
        <q-item tag="label" to="/timeline-table"  />
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {}
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 300px
  margin: 2rem
.flex-break
  display: flex
  padding: 2rem
.card-zone
  background-color: #457b9d
  text-align: center
  height: 100%
  padding: 0rem
.icon-zone
  background-color: green
  border-style: solid
  border-radius: 50%
  border-width: 3px
  color: white
  display: inline-block
  height: 100px
  width: 100px
  margin: 2rem 0rem
.card-zone-offine
  background-color: lightgray
  text-align: center
  height: 100%
.icon-zone-offine
  background-color: white
  border-style: solid
  border-color: black
  border-radius: 50%
  border-width: 3px
  color: white
  display: inline-table
  height: 100px
  width: 100px
  .fas
    padding-top: 1.3rem
    text-align: center
    color: black
    font-size: 50px
    display: inline-block
.fas
  padding-top: 1.3rem
  text-align: center
  color: white
  font-size: 50px
  display: inline-block
.tag-zone
  padding: .5rem 0rem
  magin-top: 2rem
  text-align: center
  font-size: 25px
.info-zone
  background-color: #fff
  display: space-between
  text-align: center
  color: #333
  border: 2px solid transparent
  transition: 0.3s
p
  margin: 0
.more-detail
  margin-top: 2rem
  align-items: right
</style>
