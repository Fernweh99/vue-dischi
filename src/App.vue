<template>
  <div>
    <BaseHeader @change-value="setDataForSearch" :cds="cds"/>
    <main>
      <CdCardSection :cds="cds" :labelKey="key" :valueOption="valueOption"/>
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
      valueOption: "",
      key: "",
    }
  },
  methods: {
    getCd() {
      axios.get(this.url).then(res => {
        this.cds = res.data.response
      })
    },
    setDataForSearch(value, key) {
      this.valueOption = value;
      this.key = key;
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
