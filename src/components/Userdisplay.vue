<template>
  <div class="user-card">
    <q-card class="my-card">
      <q-card-section>
        <div class="icon-zone">
          <i class="fas fa-check"></i>
        </div>
        <div class="tag-zone">
          adsfasdf
        </div>
        <div class="info-zone">
         gasggfdh
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {
  name: 'user-card',
  props: {
    userData: Array
  }
}
</script>

<style lang="scss" scoped>
.grid-item {
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 20px;
  margin: 5px;
  font-size: 30px;
  text-align: center;
  height: 120px;
}
</style>
