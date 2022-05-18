<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h3>Employé</h3>
        <h6>Nom : {{ this.employee.name }}</h6>
        <h6>Métier : {{ this.employee.metier }}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Employee",
  data() {
    return {
      employee: {
        name: 'mario',
        metier: 'ragix'
      }
    }
  }
}
</script>

<style scoped>

</style>