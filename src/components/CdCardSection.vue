<template>
  <div class="section-cd-card-">
    <div class="container">
      <div class="row g-5 row-cols-5">
        <div v-for="cd in cds" class="col" 
        :key="cd.poster"
        >
          <SingleCdCard 
          :image="cd.poster"
          :title="cd.title"
          :author="cd.author"
          :year="cd.year"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SingleCdCard from "./SingleCdCard.vue"
export default {
  name: "CdCardSection",
  components: {
    SingleCdCard,
  },
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

<style lang="scss">

</style>