<template>
  <div>
    <b-container fluid>
      <b-row style="text-align:center">
        <b-col >
          <h1>
            Stickoxide
          </h1>
          <div class="links">
            <nuxt-link to="/" class="button--grey">Karte</nuxt-link>
            <nuxt-link to="/stations" class="button--grey">Stationen</nuxt-link>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <nuxt/>
  </div>
</template>

<script>
  export default {
    components: {},
    methods: {}
  }
</script>

<style>
  html {
    font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size: 16px;
    word-spacing: 1px;
    -ms-text-size-adjust: 100%;
    -webkit-text-size-adjust: 100%;
    -moz-osx-font-smoothing: grayscale;
    -webkit-font-smoothing: antialiased;
    box-sizing: border-box;
  }

  *, *:before, *:after {
    box-sizing: border-box;
    margin: 0;
  }

  .button--grey {
    display: inline-block;
    border: 1px solid #35495e;
    color: #35495e;
    text-decoration: none;
    padding: 10px 30px;
    /* margin-left: 15px; */
  }

  .button--grey:hover {
    color: #fff;
    background-color: #35495e;
  }

  .container {
    display: flex;
    justify-content: left;
    align-items: left;
    text-align: left;
  }

  .links {
    margin-bottom: 1rem;
  }

</style>
