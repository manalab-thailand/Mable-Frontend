<template>
  <div>
    <q-tabs v-model="tab" class="tab-zone">
      <q-tab name="mails" label="Dairy" />
      <q-tab name="alarms" label="Weekly" />
      <q-tab name="movies" label="Monthly" />
    </q-tabs>
    <table>
      <tr>
        <th>No.</th>
        <th>Name</th>
        <th>Time start</th>
        <th>Time stop</th>
        <th>Location</th>
        <th>Timeline</th>
      </tr>
      <tr>
        <td>1.</td>
        <td>Yatogami Tohka</td>
        <td>08.35</td>
        <td>12.41</td>
        <td>1207</td>
        <td><span class="material-icons"> room </span></td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {}
</script>

<style lang="sass" scoped>
.tab-zone
  margin:2 rem
table
  margin: 2rem
  width: 100%
  border-style: solid
  display: space-between
tr
  border-style: solid
  text-align: center
td
  border-style: solid
  border-left: hidden
  border-right: hidden
</style>
