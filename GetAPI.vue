<template>
  <div>
    <h1>Get API Component</h1><!--
    <div>
      <table class="center" border="1" cellpadding="4" cellspacing="15">
        <tr>
          <th>Name</th>
          <th>Salary</th>
          <th>Age</th>
        </tr>
        <tr v-for="i in list" v-bind:key="i">
          <td>{{ i.employee_name }}</td>
          <td>{{ i.employee_salary }}</td>
          <td>{{ i.employee_age }}</td>
        </tr>
      </table>
    </div>-->
    <div>{{errored}}</div>
    <div>
      <table class="center" border="1" cellpadding="4" cellspacing="15">
        <tr>
          <th>ID</th>
          <th>NAME</th>
          <th>EMAIL</th>
          <th>ADDRESS</th>
        </tr>
        <tr v-for="i in list" v-bind:key="i">
          <td>{{ i.id }}</td>
          <td>{{ i.name }}</td>
          <td>{{ i.email }}</td>
          <td>{{ i.address }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";

Vue.use(VueAxios, axios);

export default {
  name: "GetAPI",
 // url1: "http://dummy.restapiexample.com/api/v1/employees",
  //url2: "http://localhost:9090/restaurants",
  mounted() {
    Vue.axios.get("http://localhost:9090/restaurants").then((res) => {
      this.list = res.data;
      console.log(res.data)
    }).catch( error => {
      console.warn(error)
      this.errored = error
     }).finally(()=>this.warn("Not loaded"));
  },

  data() {
    return {
      list: undefined,
      errored: undefined
    };
  },
};
</script>

<style scoped>
.center {
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50px;
}
</style>
