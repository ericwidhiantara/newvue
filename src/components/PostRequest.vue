<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="card text-center m-3">
      <h5 class="card-header">POST Request with Set Headers</h5>
      <div class="card-body">Returned Id: {{ articleId }}</div>
      <div class="card-body">Returned Message: {{ message }}</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "PostRequest",
  props: {
    msg: String,
  },
  data() {
    return {
      articleId: null,
      message: null,
    };
  },
  created() {
    // POST request using axios with set headers
    const body = { niu: "201701123", tahun: "2022", bulan: "04" };
    const headers = {
      Authorization:
        "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VybmFtZSI6InNpYWJzZW5zaSIsImlhdCI6MTY1MDM0MjQyNSwiZXhwIjoxNjUwNDI4OTI1fQ.UPOk74EO4g1Iyp9hLGC-Dlbqj7vwOe2qcLpyU-g1JR4",
      // "My-Custom-Header": "foobar"
    };
    axios
      .post(
        "https://absensi.undiksha.ac.id/services/absensi/history_presensi",
        body,
        { headers }
      )
      .then((response) => {
        this.articleId = response.data.id;
        this.message = response.data;
      });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
