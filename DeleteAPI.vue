<template>
  <div class="c1">
    <h1>Delete API Component</h1>
    <div>
      <table class="c1" border="1" cellpadding="4" cellspacing="15">
        <tr>
          <th>ID</th>
          <th>NAME</th>
          <th>EMAIL</th>
          <th>ADDRESS</th>
          <th>ACTION</th>
        </tr>
        <tr v-for="i in list" v-bind:key="i">
          <td>{{ i.id }}</td>
          <td>{{ i.name }}</td>
          <td>{{ i.email }}</td>
          <td>{{ i.address }}</td>
          <td><button v-on:click="deleteResto(i.id)">Delete</button></td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "DeleteAPI",
  mounted() {
    this.getResto();
  },
  methods: {
    getResto() {
      Vue.axios.get("http://localhost:9090/restaurants").then((res) => {
        this.list = res.data;
        console.log(this.list);
      });
    },
    deleteResto(id){
        Vue.axios.delete("http://localhost:9090/restaurants/"+id).then((res) => {
        this.list = res.data;
        console.log(this.list);
      });
    },
  },
  data() {
    return {
      list: null,
    };
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
