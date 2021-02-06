<template>
    <q-page class="q-page-register" style="max-width: 300px">
        <div class="text-h4">
                Register
        </div>
      <div class="q-register-box">
      <q-input
        filled
        v-model="name"
        label="Name"
        mask="###/##"
        hint="ex: John Arnont"
      />

      <q-input
        filled
        v-model="phone"
        label="Phone"
        mask="(###) ### - ####"
        hint="ex: 0925555555"
      />

      <q-input
        filled
        v-model="type"
        label="Type"
        mask="AAAA - #### - #### - SSS"
        hint="ex: Samsung Galaxy S30 Mega"
      />
      <q-btn to="/dashboard" label="Register" color="primary"/>
    </div>
    </q-page>
</template>

<script>
export default {
  data () {
    return {
      name: null,
      phone: null,
      type: null,
      location: null
    }
  }
}
</script>

<style lang="scss" scoped>
.q-page-register{
    margin: auto;
    width: 60%;;
    padding: 10px;
    padding-top: 10%;
}
.q-register-box{
    margin-top: 20px;
    background-color: antiquewhite;
    padding: 5px;
}
</style>
