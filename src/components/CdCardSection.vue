<template>
  <div class="section-cd-card-">
    <div class="container">
      <div class="row g-5 row-cols-5">
        <div v-for="cd in getFilteredArray" class="col" 
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
import SingleCdCard from "./SingleCdCard.vue"
export default {
  name: "CdCardSection",
  props: {
    cds: Array,
    valueOption: String,
    labelKey: String,
  },
  components: {
    SingleCdCard,
  },
  computed: {
    getFilteredArray() {
      return this.cds.filter((cd)=> {
        const currentTextKey = cd[this.labelKey];
        if (!this.valueOption) return true;
        else if(currentTextKey == this.valueOption) {
          return true;
        }
        else return false
      })
    },
  }
}
</script>

<style lang="scss">

</style>