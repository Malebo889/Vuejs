<template>
  <div class="principal-page">
    <div class="row">
      <div class="col-sm-12">
        <h3>User List</h3>
        <ul>
          <li v-for="user in user" :key="user">
            {{ user }}
            </li>
        </ul>
      </div>
    </div>
    <!-- row -->
  </div>
</template>
<script>
import axios from "axios";

export default {
  data() {
    return {
      user: []
    };
  },
  methods: {
    getAPI() {
      axios.get("http://localhost:3000/api/user").then(res => {
        this.user = res.data;
      });
    }
  },
  mounted() {
    this.getAPI();
  }
};
</script>
<style scoped>
.principal-page {
  margin: auto;
  padding: 12%;
}
</style>
