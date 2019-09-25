<template>
  <div class="container-fluid full-height homepage-wrapper text-center relative">
    <div class="homepage-copyright-footer"> © 2019 FreeAtlantaMove.com </div>
    <div class="row">
      <div class="col-sm-12 col-md-12 col-lg-12">
        <img class="homepage-logo" src="../assets/fam-truck-with-white-text.png" />
        <p class="homepage-form-header"> You are only one step from a FREE move! </p>
      </div>
      <div class="col-sm-12 col-md-12 col-lg-12">
        <form action="/" method="GET">
          <label class="homepage-form-label"> Email: </label>
          <input type="text" class="homepage-form-input" />
          <input type="submit" class="homepage-form-submit" value="Submit" />
        </form>
      </div>
    </div>
  </div>
</template>

<style>
  .homepage-wrapper {
    background: url('../assets/fam-homepage-background.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }

  .homepage-logo {
    width: 50%;
    min-width: 290px;
    max-width: 600px;
    margin: 90px 0 55px 0;
  }

  .homepage-form-header {
    color: #F5F5F5;
    font-size: 20px;
    margin: 0 0 20px 0;
  }

  .homepage-form-label {
    color: #F5F5F5;
    display: inline-block;
    font-size: 17px;
    padding-right: 10px;
  }

  .homepage-form-input {
    outline: none !important;
    border: 1px solid #e3e3e3;
    padding: 5px 11px;
    width: 100%;
    max-width: 230px;
    border-radius: 4px;
    transition: all 250ms;
  }

  .homepage-form-input:focus,
  .homepage-form-input:active,
  .homepage-form-input:hover {
    border: 1px solid #0275db;
  }

  .homepage-form-submit {
    display: block;
    margin: 20px auto;
    border: 2px solid #F5F5F5;
    background: #ca2626;
    color: #F5F5F5;
    font-weight: 600;
    font-size: 15px;
    border-radius: 50px;
    padding: 6px 33px;
    outline: none !important;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    transition: all 250ms;
  }

  .homepage-form-submit:hover,
  .homepage-form-submit:active,
  .homepage-form-submit:focus {
    filter: brightness(95%);
  }

  .homepage-copyright-footer {
    position: absolute;
    text-align: left;
    bottom: 30px;
    left: 45px;
    color: #F5F5F5;
  }
</style>

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
