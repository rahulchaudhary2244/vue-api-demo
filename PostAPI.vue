<template>
  <div>
    <div>
      <h1>Post API Component</h1>
      <br >
    </div>
    <div>
      <form @submit="submitData" method="post">
        <input type="text" v-model="info.id" name="id" placeholder="Enter Id" />
        <br /><br />
        <input
          type="text"
          v-model="info.name"
          name="name"
          placeholder="Enter Name"
        />
        <br /><br />
        <input
          type="email"
          v-model="info.email"
          name="email"
          placeholder="Enter Email"
        />
        <br /><br />
        <input
          type="text"
          v-model="info.address"
          name="address"
          placeholder="Enter Address"
        />
        <br /><br />
        <button type="submit">Add Resto</button>
      </form>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "PostAPI",
  methods: {
    submitData(e) {
      this.axios
        .post("http://localhost:9090/restaurants", this.info)
        .then((res) => {
          console.warn(res);
          this.info.id = null;
          this.info.name = null;
          this.info.email = null;
          this.info.address = null;
        });
      e.preventDefault();
    },
  },
  data() {
    return {
      info: {
        id: null,
        name: null,
        email: null,
        address: null,
      },
    };
  },
};
</script>
