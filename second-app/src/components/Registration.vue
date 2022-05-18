<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-md-3">
        <div class="card">
          <div class="card-header bg-success text-white ">
            <h3>Register Here</h3>
          </div>
          <div class="card-body bg-light">
            <form @submit.prevent="register()">
              <div class="mb-2">
                <input v-model="user.name" type="text" class="form-control" placeholder="name">
              </div>
              <div class="mb-2">
                <input v-model="user.email" type="email" class="form-control" placeholder="email">
              </div>
              <div class="mb-2">
                <input v-model="user.password" type="password" class="form-control" placeholder="password">
              </div>
              <div class="mb-2">
                <input class="btn btn-outline-success" value="Enregistrer" type="submit">
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Registration",
  data() {
    return {
      user: {
        name: '',
        email: '',
        password: '',
      }
    }
  },
  methods: {
    register() {
      console.log(this.user)
    }
  }
}
</script>

<style scoped>

</style>