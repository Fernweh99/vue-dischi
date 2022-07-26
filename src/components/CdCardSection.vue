<template>
  <div class="section-cd-card-">
    <div class="container">
      <div class="row g-5 row-cols-5">
        <div v-for="cd in cds" :key="cd.poster" class="col">
          <div class="cd-card h-100">
            <img class="img-fluid" :src="cd.poster" :alt="cd.title">
            <div class="cd-info text-center">
              <h4 class="cd-title">{{ cd.title }}</h4>
              <span class="cd-moreinfo">
                {{ cd.author }}<br/>
                {{ cd.year }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "CdCardSection",
  data() {
    return {
      url: "https://flynn.boolean.careers/exercises/api/array/music",
      cds: [],
    }
  },
  methods: {
    getCd () {
      axios.get(this.url).then(res => {
        this.cds = res.data.response
      })
    }
  },
  mounted() {
    this.getCd();
  }

}
</script>

<style lang="scss" scoped>
  @import "../assets/scss/vars.scss"; 
  .cd-card {
    padding: 15px;
    background-color: $primary_color;
    .cd-info {
      .cd-title {
        text-transform: capitalize;
        color: white;
      }
      .cd-moreinfo {
        color: gray;
      }
    }
  }
</style>