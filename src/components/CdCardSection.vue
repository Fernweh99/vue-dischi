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
import SingleCdCard from "./SingleCdCard.vue"
export default {
  name: "CdCardSection",
  props: {
    cds: Array,
  },
  components: {
    SingleCdCard,
  },
}
</script>

<style lang="scss">

</style>