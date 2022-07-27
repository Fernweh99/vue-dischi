<template>
  <div>
    <BaseHeader :cds="cds"/>
    <main>
      <CdCardSection :cds="cds"/>
    </main>
  </div>
</template>

<script>
import axios from "axios";
import BaseHeader from "./components/BaseHeader.vue"
import CdCardSection from "./components/CdCardSection.vue"

export default {
  name: 'App',
  components: {
    BaseHeader,
    CdCardSection,
  },
  data() {
    return {
      url: "https://flynn.boolean.careers/exercises/api/array/music",
      cds: [],
    }
  },
  methods: {
    getCd() {
      axios.get(this.url).then(res => {
        this.cds = res.data.response
      })
    }
  },
  created() {
    this.getCd()
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss"
</style>
