<template>
  <div class="cd-card h-100">
    <img class="img-fluid" :src="image" :alt="title">
    <div class="cd-info text-center">
      <h4 class="cd-title">{{ title }}</h4>
      <span class="cd-moreinfo">
        {{ author }}<br/>
        {{ year }}
      </span>
    </div>
  </div>  
</template>

<script>
export default {
  name: "SingleCdCard",
  props: {
    image: String,
    author: String,
    title: String,
    year: String,
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