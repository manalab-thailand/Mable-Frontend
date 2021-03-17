<template>
    <q-page class="flex flex-center">
    <div class="q-pa-md"
    style="max-width: 400px;
    margin: auto;
    width: 60%;;
    padding: 10px;">
    <div class="row text-primary" style="margin-bottom:40px;">
       <div class="text-h3">Login</div>
    </div>
        <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Username"
        hint="Username or email"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type username or email']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Password"
        hint="Password"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'Please type your password',
          val => val.length >= 8|| 'Password must be than 8 charector'
        ]"
      />
      <div class="mt-center">
        <q-btn to="/index" label="Login" type="submit" color="primary"/>
      </div>
    </q-form>
    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      username: null,
      password: null,
      save_password: false
    }
  },
  methods: {
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      } else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },
    onReset () {
      this.name = null
      this.age = null
      this.accept = false
    }
  }
}
</script>

<style lang="scss" scoped>
$center: center;
.mt-center{
  width: 100%;
    text-align: $center;
}
.logo-image{
  width: 100%;
}
.center{
    margin: auto;
    width: 60%;;
    padding: 10px;
}
</style>
