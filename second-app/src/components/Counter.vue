<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-4">
        <div class="card shadow-lg">
          <div class="card-body">
            <p class="h3 display-3">Count : {{ count }}</p>

            <button @click="OnMinus" class="btn btn-outline-danger me-3">-</button>
            <button @click="OnPlus" class="btn btn-outline-success">+</button>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return {
      count: 0
    }
  },
  methods: {
    OnPlus() {
      this.count++
    },
    OnMinus() {
      this.count--
    }
  }
}
</script>

<style scoped>

</style>