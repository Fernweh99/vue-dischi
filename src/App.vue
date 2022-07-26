<template>
  <div>
    <BaseHeader/>
    <main>
      <CdCardSection/>
    </main>
  </div>
</template>

<script>
import BaseHeader from "./components/BaseHeader.vue"
import CdCardSection from "./components/CdCardSection.vue"

export default {
  name: 'App',
  components: {
    BaseHeader,
    CdCardSection,
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss"
</style>
