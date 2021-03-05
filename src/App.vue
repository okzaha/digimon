<template>
  <div id="app">
    <b-navbar type="dark" variant="danger">
      <b-navbar-nav>
        <b-img src="https://i.redd.it/pu6h3f3k4ea31.jpg" width="50"></b-img>
        <b-nav-item to="/">หน้าร้านค้า</b-nav-item>
        <h3></h3>
      </b-navbar-nav>
    </b-navbar>

    <router-view />
    <d>
      <b-icon
        icon="house-door-fill"
        animation="spin"
        font-scale="1"
        class="rounded-circle bg-danger p-2"
        variant="light"
      ></b-icon
      ><ddd> GA</ddd><d>MES</d>
      <b-icon
        icon="house-door-fill"
        animation="spin"
        font-scale="1"
        class="rounded-circle bg-danger p-2"
        variant="light"
      ></b-icon>
    </d>
    <br />
    <b-container class="bv-example-row">
      <b-row>
        <b-col cols="3" v-for="gamegaga in httpdata" :key="gamegaga">
          <b-card
            :img-src="gamegaga.thumbnail"
            :title="gamegaga.title"
            img-alt="หน้านิ"
            img-top
            tag="article"
            style="max-width: 20rem"
            class="mb-2"
          >
          </b-card>
        </b-col>
      </b-row>
    </b-container>
   
  </div>
</template>

<style lamg="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  font-family: "Fira Sans", sans-serif;
}
a {
  text-emphasis: none;
}

ddd {
  color: rgb(241, 69, 69);
  font-size: 42px;
  font-weight: 40px;
  text-align: center;
  text-transform: uppercase;
}
d {
  color: rgb(102, 4, 4);
  font-size: 42px;
  font-weight: 40px;
  text-align: center;
  text-transform: uppercase;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}
</style>

<script>
import axios from "axios";
export default {
  props: {
    title: String,
    image: String,
  },
  data() {
    return {
      httpdata: {},
    };
  },
  mounted() {
    axios({
      method: "GET",
      url: "https://gamerpower.p.rapidapi.com/api/giveaways",
        headers: {
    'x-rapidapi-key': '2e8b019e36mshd8474aef510db3dp16c632jsn2fb014418a7d',
    'x-rapidapi-host': 'gamerpower.p.rapidapi.com'
  }
    }).then((result) => {
      this.httpdata = result.data;
    });
  },
};
</script>