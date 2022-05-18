<template>

  <div class="container mt-4">
    <div class="row">
      <div class="col">
        <h3>App Component</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda aut cupiditate distinctio dolores eveniet
          fugiat iste, iure nemo odit placeat praesentium quam quibusdam quisquam quo sequi ullam veniam voluptate.
          Molestiae.</p>
      </div>
    </div>

    <Customer :name=name metier="Champion"/>
    <Employee/>


  </div>

  <RouterView/>
</template>

<script>
import Customer from '@/components/Customer.vue';
import Employee from '@/components/Employee.vue';

export default {
  components: {
    Customer,
    Employee
  },
  data() {
    return {
      name: 'Luigi'
    }
  }
}
</script>

<style>
@import "./styles.css";
</style>
