<template>
  <div>
    <h1>Put API Component</h1>
    
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
    name:'PutAPI',
    data() {
        return {
           
        }
    },
    methods: {

    },
}
</script>

<style scoped>
.center {
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 50px;
}
</style>