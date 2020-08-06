<template>
  <div class="home">
    <h1>{{ msg }}</h1>
    <h5>{{ sub }}</h5>
    <b-badge variant="info">{{ views === 0 ? 'Loading...' : 'This site has been visited ' + views + ' times!' }}</b-badge>
    <br /><br /><br /><br />
    <b-button href="https://drive.google.com/file/d/151aTF7Z7wiRMGOYIrxgmWPfzOG1Ae05L/view?usp=sharing" variant="primary">My Resume!</b-button>
    <br /><br /><br /><br />
    <h3>Are you bored?</h3>
    <h4>{{ activity }}<b-button pill size="sm" @click="getActivity()"><img src="../assets/refresh.png" width="10" height="10" /></b-button></h4>
  </div>
</template>

<script>
const countapi = require('countapi-js');
const axios = require('axios').default;

export default {
  name: 'Home',
  props: {
    msg: String,
    sub: String
  },
  data: function () {
    return {
      views: 0,
      activity: ''
    }
  },
  mounted: function () {
    this.getViewCount()
    this.getActivity()
  },
  methods: {
    getViewCount: function () {
      countapi.visits('global').then((result) => {
        this.views = result.value
      });
    },
    getActivity: function () {
      axios
        .get("https://www.boredapi.com/api/activity?participants=1")
        .then((res) => {
          this.activity = res.data.activity + '. '
        })
    }
  }
}
</script>
