<template>
  <div class="c1">
    <h1>Get By Id API</h1>
    <br />
    <div>
      <input type="text" placeholder="Enter Restaurant Id" v-model="id" /><br />
      <br /><button v-on:click="getById(id)">Search</button>
    </div>
    <table class="c1" border="1" cellpadding="4" cellspacing="15">
      <tr>
        <th>ID</th>
        <th>NAME</th>
        <th>EMAIL</th>
        <th>ADDRESS</th>
      </tr>
      <tr>
        <td>{{ info.id }}</td>
        <td>{{ info.name }}</td>
        <td>{{ info.email }}</td>
        <td>{{ info.address }}</td>
      </tr>
    </table>
  </div>
</template>
<script>
import Vue from "vue";
import VueAxios from "vue-axios";
import axios from "axios";

Vue.use(VueAxios, axios);

export default {
  name: "GetAPIById",
  data() {
    return {
      id:String,
      error: undefined,
      info: undefined,
    };
  },
  methods: {
    getById(id) {
      Vue.axios
        .get("http://localhost:9090/restaurants/"+id)
        .then((x) => {
          this.info = x.data, 
          console.warn(id);
        })
        .catch((error) => (this.error = error));
    },
  },

};
</script>

<style scoped>
.c1 {
  margin-left: auto;
  margin-right: auto;
  margin-top: 50px;
  margin-bottom: 50px;
}
</style>
