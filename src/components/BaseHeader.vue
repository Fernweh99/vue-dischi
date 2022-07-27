<template>
  <header>
    <div class="container h-100 d-flex align-items-center justify-content-between">
      <div class="logo text-white">Logo</div>
      <SelectComponent :cds="cds" label-key="genre"/>
    </div>
  </header>
</template>

<script>
import SelectComponent from "./SelectComponent.vue"

export default {
  name: "BaseHeader",
  components: {
    SelectComponent,
  },
  props: {
    cds: Array,
  },
  data() {
    return {
      valueOption: "",
    }
  },
}
</script>

<style lang="scss">
  @import "../assets/scss/vars";
  header {
    background-color: $primary_color;
    height: 70px;
  }
</style>