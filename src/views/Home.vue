<template>
  <div>
    <h1> Welcome Home </h1>
  </div>
</template>

<script>
  import axios from "axios";

  export default {
    data() {
      return {
        loading: false
      };
    },

    submitForm() {
      // Example axios request:
      axios
       .get('https://api.coindesk.com/v1/bpi/currentprice.json')
       .then(response => { this.data = response.data.bpi })
       .catch(error => { alert(error) })
       .finally(() => this.loading = false);
    }
  };
</script>
