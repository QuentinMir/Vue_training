<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h2>App customer</h2>
        <h6>Nom : {{ name }}</h6>
        <h6>Métier : {{ metier }}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Customer",
  props: ['name', 'metier']
}
</script>

<style scoped>

</style>