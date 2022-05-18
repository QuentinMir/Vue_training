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

    <Counter/>

    <Registration/>

    <table class="table">
      <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Name</th>
        <th scope="col">Email</th>
        <th scope="col">Company</th>
        <th scope="col">Website</th>
        <th scope="col">Location</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="user of users" :key="user.id">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.email }}</td>
        <td>{{ user.company.name }}</td>
        <td>{{ user.website }}</td>
        <td>{{ user.address.city }}</td>
      </tr>
      </tbody>
    </table>


  </div>

  <RouterView/>
</template>

<script>
import Customer from '@/components/Customer.vue';
import Employee from '@/components/Employee.vue';
import Counter from '@/components/Counter.vue';
import Registration from '@/components/Registration.vue';
import {UserService} from "./components/services/UserService";

export default {
  components: {
    Customer,
    Counter,
    Registration,
    Employee
  },
  data() {
    return {
      name: 'Luigi',
      users: [],
      loading: false,
      errorMsg: null
    }
  },
  created: async function () {
    try {
      this.loading = true;
      let response = await UserService.getAllUsers();
      this.loading = false;
      this.users = response.data;
      console.log(this.users)
    } catch (error) {
      this.loading = false;
      this.errorMsg = error;
    }
  }
}
</script>

<style>
@import "./styles.css";
</style>
